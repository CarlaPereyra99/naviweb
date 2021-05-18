<template>
  <div>
    <v-navigation-drawer v-model="drawer" app right>
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-home</v-icon>
          </v-list-item-action>

          <v-list-item-content>
            <router-link style="text-decoration: none; color: black" to="/">
              <v-list-item-title> Home </v-list-item-title>
            </router-link>
          </v-list-item-content>
        </v-list-item>

        <v-list-item link v-if="session">
          <v-list-item-action>
            <v-icon>mdi-login</v-icon>
          </v-list-item-action>

          <v-list-item-content>
            <router-link
              style="text-decoration: none; color: black"
              to="/Login"
            >
              <v-list-item-title> Inciar Sesión </v-list-item-title>
            </router-link>
          </v-list-item-content>
        </v-list-item>

        <v-list-item v-if="!session" link>
          <v-list-item-action>
            <v-icon>mdi-face</v-icon>
          </v-list-item-action>

          <v-list-item-content>
            <router-link
              style="text-decoration: none; color: black"
              to="/Profile"
            >
              <v-list-item-title> Ver Perfil </v-list-item-title>
            </router-link>
          </v-list-item-content>
        </v-list-item>

        <v-list-item link v-if="!session">
          <v-list-item-action>
            <v-icon>mdi-upload</v-icon>
          </v-list-item-action>

          <v-list-item-content>
            <router-link
              style="text-decoration: none; color: black"
              to="/Upload"
            >
              <v-list-item-title> Subir Juego </v-list-item-title>
            </router-link>
          </v-list-item-content>
        </v-list-item>

        <v-list-item v-if="!session" link>
          <v-list-item-action>
            <v-icon>mdi-logout</v-icon>
          </v-list-item-action>

          <v-list-item-content @click="logout">
            <v-list-item-title> Cerrar Sesión </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="black" dark>
      <v-spacer></v-spacer>

      <v-toolbar-title>Navi - Hey Listen!</v-toolbar-title>

      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      drawer: false,
      session: false,
    };
  },
  created() {
    this.session = localStorage.getItem("usuario") ? false : true;
  },
  methods: {
    logout() {
      localStorage.removeItem("usuario");
      window.location.href = "/";
    },
  },
};
</script>
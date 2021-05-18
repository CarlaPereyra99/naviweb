<template>
  <div>
    <Header />
    <v-main>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col cols="12" sm="8" md="4">
            <v-card class="elevation-12">
              <v-toolbar color="black" dark flat>
                <v-toolbar-title>Inciar Sesion</v-toolbar-title>
              </v-toolbar>
              <v-card-text>
                <v-form>
                  <v-text-field
                    v-model="user"
                    label="Usuario o Nickname"
                    prepend-icon="mdi-account"
                    type="text"
                  ></v-text-field>

                  <v-text-field
                    v-model="password"
                    id="password"
                    label="Password"
                    prepend-icon="mdi-lock"
                    type="password"
                  ></v-text-field>
                </v-form>
                <router-link to="/SignUp">
                  ¿Aun no tienes cuenta? ¡Registrate!
                </router-link>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn @click="login" color="black" text>Aceptar</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";

export default {
  components: {
    Header,
    Footer,
  },
  data: () => {
    return {
      user: "",
      password: "",
    };
  },
  methods: {
    async login() {
      const resp = await fetch("http://localhost:4000/api/user/login", {
        method: "post",
        body: JSON.stringify({
          email: "hector.hdz2807@gmail.com",
          password: "123456",
        }),
        headers: {
          "Content-Type": "application/json",
        },
      }).then((res) => {
        return res.json();
      });

      console.log("[resp]", resp);
      if (resp.ok) {
        localStorage.setItem("usuario", resp.userDB._id);
        window.location.href = "/";
      } else {
        alert("Error");
      }
    },
  },
};
</script>

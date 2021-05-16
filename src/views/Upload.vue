<template>
  <div>
    <Header />
    <v-main>
      <v-row justify="center">
        <v-col cols="12" sm="10" md="8" lg="6">
          <v-card ref="form">
            <v-card-text>
              <v-text-field
                v-model="name"
                label="Nombre del Juego"
                prepend-icon="mdi-gamepad"
                placeholder="Ingrese el nombre del juego"
                required
              ></v-text-field>
              <v-text-field
                v-model="genre"
                label="Genero"
                prepend-icon="mdi-shape-plus"
                placeholder="Ingrese el genero del Juego"
                required
              ></v-text-field>
              <v-file-input
                v-model="img"
                accept="image/png, image/jpeg, image/bmp"
                placeholder="Escoge la miniatura del juego"
                prepend-icon="mdi-camera"
                label="Miniatura del Juego"
              ></v-file-input>
              <v-text-field
                v-model="website"
                label="website"
                prepend-icon="mdi-web"
                placeholder="Ingrese el genero del Juego"
                required
              ></v-text-field>
            </v-card-text>
            <v-card-actions>
              <v-btn color="red" text>Cancel</v-btn>
              <v-spacer></v-spacer>

              <v-btn color="black" text @click="submit">Subir</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
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
      name: "",
      genre: "",
      website: "",
      img: null,
    };
  },
};
</script>

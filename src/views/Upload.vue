<template>
  <div>
    <Header />
    <v-main>
      <v-row justify="center">
        <v-col cols="12" sm="10" md="8" lg="6">
          <v-card ref="form">
            <v-card-title primary-title> SUBIR JUEGO NUEVO </v-card-title>
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
                label="website (opcional)"
                prepend-icon="mdi-web"
                placeholder="Ingrese el genero del Juego"
                required
              ></v-text-field>
            </v-card-text>
            <v-card-actions>
              <v-btn color="red" text>Cancel</v-btn>
              <v-spacer></v-spacer>

              <v-btn color="black" text @click="upload">Subir</v-btn>
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
import swal from "sweetalert2";

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
  methods: {
    async upload() {
      if (this.name && this.genre && this.img) {
        const response = await fetch("http://localhost:4000/api/game/", {
          method: "post",
          body: JSON.stringify({
            id: localStorage.getItem("usuario"),
            name: this.name,
            genre: this.genre,
            website: this.website,
            image: this.img.name,
          }),
          headers: {
            "Content-Type": "application/json",
          },
        });

        if (response.ok) {
          new swal("Listo!", "Se subio el videojuego exitosamente", "success");
        } else {
          new swal("Error", "Revisa tu conexion a internet", "error");
        }
      } else {
        new swal("Error", "Hay Campos Obligatorios Vacios", "error");
      }
    },
  },
};
</script>

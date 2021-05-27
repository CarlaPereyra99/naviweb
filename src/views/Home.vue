<template>
  <div class="home">
    <Header />
    <v-main>
      <v-card color="red accent-4">
        <v-img src="../assets/cover-page.webp" />
        <v-card-title class="text-center justify-center">
          <v-text-field
            v-model="search"
            label="Busqueda"
            placeholder="¿Qué quieres buscar?"
            filled
            rounded
            dense
            prepend-inner-icon="mdi-magnify"
            outlined
          ></v-text-field>
        </v-card-title>

        <v-tabs v-model="tab" background-color="transparent" color="white" grow>
          <v-tab v-for="item in items" :key="item">
            {{ item }}
          </v-tab>
        </v-tabs>
      </v-card>

      <h1>Juegos destacados de la semana</h1>
      <Carousel class="mt-2" />
    </v-main>
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header";
import Footer from "@/components/Footer";
import Carousel from "@/components/Carousel";

export default {
  name: "Home",
  components: {
    Header,
    Footer,
    Carousel,
  },
  data: () => {
    return {
      search: "",
      tab: "",
      items: ["Juegos", "Genero", "Desarrollador"],
    };
  },
};
</script>

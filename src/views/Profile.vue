<template>
  <div>
    <Header />
    <v-main>
      <v-row>
        <v-col col="2">
          <v-card width="250">
            <v-img
              elevation-21
              src="https://pbs.twimg.com/profile_images/1154136875096932352/llORv2Ir_400x400.jpg"
              contain
            ></v-img>
          </v-card>
        </v-col>
        <v-col cols="8">
          <h2 class="ml-3"><strong>Nombre:</strong> Hector Hernandez</h2>
          <h2 class="ml-3"><strong>Nickname:</strong> NaerHdz</h2>
        </v-col>
      </v-row>
      <Carousel class="mt-1" />
    </v-main>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header";
import Carousel from "@/components/Carousel";
import Footer from "@/components/Footer";

export default {
  components: {
    Header,
    Carousel,
    Footer,
  },
  data: () => {
    return {
      colors: [
        "indigo",
        "warning",
        "pink darken-2",
        "red lighten-1",
        "deep-purple accent-4",
      ],
      slides: [1, 2, 3, 4, 5],
    };
  },
};
</script>
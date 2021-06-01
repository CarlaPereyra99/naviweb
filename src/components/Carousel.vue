<template>
  <center>
    <div>
      <h1>BIENVENDIDO(A)</h1>
    </div>
    <v-carousel
      v-model="model"
      cycle
      hide-delimiter-background
      show-arrows-on-hover
      style="width: 90%; border-radius: 50px"
    >
      <v-carousel-item
        style="border-radius: 50px"
        v-for="juego in juegos"
        :key="juego"
        :src="juego"
      >
        <!-- <v-sheet max-width="70%" class="mt-10">
          <v-row class="fill-height" align="center" justify="center">
            <v-img aspect-ratio="1.8" :src="juego" />
          </v-row>
        </v-sheet> -->
      </v-carousel-item>
    </v-carousel>
  </center>
</template>

<script>
export default {
  data: () => {
    return {
      model: 0,
      juegos: [
        require("../assets/kof97_detail.png"),
        require("../assets/metal-slug-release-date.jpg"),
        require("../assets/smash_pelea.jpg"),
        require("../assets/coverpokemon.jpg"),
      ],
    };
  },
};
</script>

<style>
h1 {
  color: white;
}
</style>
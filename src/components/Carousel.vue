<template>
  <center>
    <v-carousel
      v-model="model"
      cycle
      hide-delimiter-background
      show-arrows-on-hover
    >
      <v-carousel-item v-for="color in colors" :key="color">
        <v-sheet height="50px" max-width="90%">
          <v-row class="fill-height" align="center" justify="center">
            <!-- <div class="display-3">Slide {{ i + 1 }}</div> -->
            <v-img aspect-ratio="2" :src="color" />
          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
  </center>
</template>

<script>
export default {
  data: () => {
    return {
      model: 0,
      colors: [
        require("../assets/kof.jpg"),
        require("../assets/metal slug.jpg"),
        require("../assets/smashbros.jpg"),
      ],
    };
  },
};
</script>

<template>
  <center>
    <v-carousel
      v-model="model"
      cycle
      hide-delimiter-background
      show-arrows-on-hover
    >
      <v-carousel-item v-for="color in colors" :key="color">
        <v-sheet height="100%" max-width="68%">
          <v-row class="fill-height" align="center" justify="center">
            <!-- <div class="display-3">Slide {{ i + 1 }}</div> -->
            <v-img aspect-ratio="1.5" max-width="90%" :src="color" />
            <v-card height="500px" dark>
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title class="headline"> Titulo </v-card-title>
                </div>
              </div>

              <div>
                <v-avatar class="ma-3" size="125" tile>
                  <v-img src="../assets/intro.jpg"></v-img>
                </v-avatar>
              </div>

              <div>
                <v-avatar class="ma-3" size="125" tile>
                  <v-img src="../assets/pokemon_batalla.jpg"></v-img>
                </v-avatar>
              </div>
            </v-card>
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
        require("../assets/coverpokemon.jpg"),
      ],
    };
  },
};
</script>

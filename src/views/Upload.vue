<template>
  <div>
    <Header />
    <v-main>
      <h1>Soy el upload</h1>
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
};
</script>

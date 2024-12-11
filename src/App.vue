<template>
  <div>
    <Header />
    <Main>
      <Grid/>
    </Main>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";
import Grid from "./components/Grid.vue";

export default {
  name: "App",
  components: {
    Grid,
    Header,
    Main,
    Footer,
  },
};
</script>

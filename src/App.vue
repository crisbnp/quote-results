<template>
  <v-app class="app">
    <v-app-bar app color="black">
      <div class="d-flex align-center">
        <v-img
          alt="Paymentshield Logo"
          class="shrink mr-2"
          contain
          src="./assets/white_logo.png"
          transition="scale-ransition"
          width="160"
        />
      </div>

      <v-spacer></v-spacer>

      <div class="white--text text-uppercase">
        <p>Quote reference 
          <br> 
          PSL-BCHI-1234567
        </p>
      </div>
    </v-app-bar>

    <v-main>
      <ProgressBar/>
      <Results/>
    </v-main>
  </v-app>
</template>

<script>
import ProgressBar from './components/ProgressBar.vue';
import Results from './components/Results.vue'

export default {
  name: "App",

  components: {
    ProgressBar,
    Results
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Lato&display=swap');
  $font-family: 'Lato', serif;
  .app {
    .headline,
    [class*='display-'],
    [class*='text-'] {
      color: #36405a;
      font-family: $font-family, sans-serif !important;
    }
    font-family: $font-family, sans-serif !important;

    .v-btn {
      background-color: #E50046 !important;
    }

    .v-main__wrap {
      background-color: #f2f2f5;
    }

    .v-sheet {
      margin: 0 auto;
    }
  }

</style>
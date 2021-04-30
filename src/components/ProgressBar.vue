<template>
  <v-tabs background-color="grey darken-3" color="white" centered>
    <v-tab class="white--text">
      <v-progress-circular
        :width="1"
        :value="100"
        color="red"
      ><span class="white--text">1</span></v-progress-circular>
        Personal Details
    </v-tab>
    <v-tab class="white--text">
      <v-progress-circular
    :width="1"
      :value="100"
      color="red"
    ><span class="white--text">2</span></v-progress-circular>
    Property Details
    </v-tab>
    <v-tab class="white--text">
    <v-progress-circular
    :width="1"
      :value="100"
      color="red"
    ><span class="white--text">3</span></v-progress-circular>
    Cover Details
    </v-tab>

    <v-tab class="white--text">
    <v-progress-circular
    :width="1"
      :value="100"
      color="red"
    ><span class="white--text">4</span></v-progress-circular>
    Previous Claims
    </v-tab>
    <v-tab class="white--text">
    <v-progress-circular
    :width="1"
      :value="100"
      color="#D1D834"
      class="activestate"
    ><span>5</span></v-progress-circular>
    Results
    </v-tab>
  </v-tabs>
</template>

<script>
export default {
  name: "ProgressBar"
}
</script>

<style lang="scss" scoped>
.v-progress-circular {
  margin: 1rem;
}

.activestate {
  background-color: #D1D834;
  border-radius: 50%;

  span {
    color: black;
  }
}
</style>

<template>
<div class="bg-dark">
  <v-stepper non-linear dark>
    <v-stepper-header>
      <v-stepper-step
        editable
        step="1"
        color="#D1D834"
      >
        Personal Details
      </v-stepper-step>
      
      <v-stepper-step
        editable
        step="2"
        color="#D1D834"
      >
        Property Details
      </v-stepper-step>

      <v-stepper-step
        editable
        step="3"
        color="#D1D834"
      >
        Cover Details
      </v-stepper-step>

      <v-stepper-step
        editable
        step="4"
        color="#D1D834"
      >
        Previous Claims
      </v-stepper-step>

      <v-stepper-step
        editable
        step="5"
        color="#D1D834"
      >
        Results
      </v-stepper-step>


    </v-stepper-header>
  </v-stepper>
</div>
</template>

<script>
export default {
  name: "ProgressBar"
}
</script>

<style lang="scss">
.bg-dark {
  background-color: #2C3536;
}

.v-stepper__step__step {
  border-radius: 50%;
  border: 1px solid red;
  background: rgba(209,216,52,0.1) !important;
}


</style>

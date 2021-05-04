<template>
  <div class="widget px-6 d-none d-sm-none d-md-block d-lg-block">
    <v-img src="../assets/defaqto-logo.png" width="200"></v-img>
    <p class="text-h6 text-center font-weight-black">Compare policies</p>
  </div>
</template>

<script>
export default {
  name: "DefaqtoWidget.vue"
}
</script>

<style scoped>
  .widget {
    background-color: white;
    float: right;
    position: absolute;
    top: 8.5rem;
    right: -62px;
    border: 1px solid black;
    transform:rotate(90deg)
  }
</style>

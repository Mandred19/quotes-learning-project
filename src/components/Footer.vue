<template>
  <div class="row">
    <div class="col">
      <hr>
      <p class="text-dark text-center">{{ footerText }}</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Footer",
    props: {
      footerText: {
        type: String,
      }
    },
  }
</script>

<style lang="scss" scoped>
  p {
    font-size: 20px;
  }
</style>

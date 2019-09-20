<template>
  <header class="row">
    <div class="col flex-column justify-content-center">
      <h1 class="card-title text-center">App Quotes</h1>
      <div class="progress">
        <div class="progress-bar"
             :style="{width: `${quoteLength * 10}%`}"
        >{{ quoteLength }} / {{ maxQuotes }}
        </div>
      </div>
      <hr>
    </div>
  </header>
</template>

<script>
  export default {
    name: "Header",
    props: {
      quoteLength: Number,
      maxQuotes: Number,
      start: Boolean,
    },
  }
</script>

<style lang="scss" scoped>
  header {
    padding-top: 20px;
  }
  
  h1 {
    font-size: 25px;
  }
  
  .progress {
    height: 1.5rem;
  }
</style>

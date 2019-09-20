<template>
  <div class="row">
    <div class="col flex-column justify-content-center align-items-center flex-md-wrap text-center">
      <ul class="list">
        <app-quote-item :message="message"
          v-for="(message, index) of quote"
          @click.native="removeQuote(index)"
        ></app-quote-item>
      </ul>
    </div>
  </div>
</template>

<script>
  import QuoteItem from './QuoteItem'
  
  export default {
    name: "GroupQuote",
    components: {
      'app-quote-item': QuoteItem,
    },
    props: {
      quote: {
        type: Array,
      },
      message: {
        type: String,
      },
    },
    methods: {
      removeQuote(index) {
        this.$emit('removeQuote', index)
      },
    },
  }
</script>

<style lang="scss" scoped>
  .list {
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start;
    padding: 0;
  }
</style>

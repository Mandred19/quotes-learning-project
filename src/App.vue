<template>
  <div class="container">
    <app-header
      :quoteLength="quote.length"
      :maxQuotes="maxQuotes"
    ></app-header>
    
    <app-text-area @addText="addText"></app-text-area>
    
    <app-group-quote
      :quote="quote"
      :message="message"
      @removeQuote="removeQuote"
    ></app-group-quote>
    
    <app-footer :footerText="footerText"></app-footer>
  </div>
</template>

<script>
  import Header from './components/Header'
  import TextArea from './components/TextArea'
  import GroupQuote from './components/GroupQuote'
  import Footer from './components/Footer'
  
  export default {
    name: 'App',
    components: {
      'app-header': Header,
      'app-text-area': TextArea,
      'app-group-quote': GroupQuote,
      'app-footer': Footer,
    },
    data() {
      return {
        message: '',
        quote: ['Quote #1'],
        maxQuotes: 10,
        footerText: 'Click on a Quote to delete it'
      }
    },
    methods: {
      addText(message) {
        if (message === undefined || message === '')
          return false
        if (this.quote.length === this.maxQuotes) {
          this.footerText = 'Maximum number of Quotes reached. Please delete Quotes!'
          return false
        }
        this.message = message
        this.quote.push(message)
        console.log(this.quote)
      },
      removeQuote(index) {
        this.quote.splice(index, 1)
      },
    },
  }
</script>

<style lang="scss">
  @import "../node_modules/bootstrap/scss/bootstrap";
  
  .container {
    height: 100vh;
  }
</style>

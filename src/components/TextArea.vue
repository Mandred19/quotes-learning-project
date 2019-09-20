<template>
  <div class="row">
    <div class="col flex-column">
      <form action="">
        <div class="form-group flex-column justify-content-center text-center">
          <label class="text-label" for="text1">Enter your text here</label>
          <textarea class="form-control"
                    id="text1"
                    rows="4"
                    v-model.lazy="message"
          ></textarea>
        </div>
      </form>
      <button type="button"
              class="btn btn-primary"
              @click.prevent="addText"
      >Add text
      </button>
      <hr>
    </div>
  </div>
</template>

<script>
  export default {
    name: "TextArea",
    data() {
      return {
        message: '',
      }
    },
    methods: {
      addText() {
        this.$emit('addText', this.message)
        this.message = ''
      }
    },
  }
</script>

<style lang="scss" scoped>
  .form-control {
    width: 50%;
    margin: 0 auto;
  }
  
  .text-label {
    font-size: 18px;
  }
  
  .btn-primary {
    display: flex;
    margin: 0 auto;
  }
</style>

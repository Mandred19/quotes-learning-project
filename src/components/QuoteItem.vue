<template>
  <li class="list__item">
    <span>{{ message }}</span>
  </li>
</template>

<script>
  export default {
    name: "QuoteItem",
    props: {
      message: {
        type: String,
      }
    },
  }
</script>

<style lang="scss" scoped>
  .list__item {
    cursor: pointer;
    margin: 10px;
    list-style: none;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 18.1%;
    height: 130px;
    border: 1px solid #999;
    border-radius: 5px;
    transition: all linear .2s;
    padding: 20px;
    font-family: Arizonia;
    overflow: auto;
    
    &:hover {
      border-color: #007bff;
      
      .close {
        visibility: visible;
      }
    }
  }
  
  .list__item span {
    font-size: 40px;
    word-break: break-word;
    line-height: 1;
  }
</style>

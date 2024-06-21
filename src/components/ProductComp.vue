<template lang="">
  {{productIsbn}}
  {{productPublisher}}
  {{productPages}}
  {{productGenre}}
  {{productYear}}
  {{productAuthor}}
    {{productName}}

  </template>
  <script>
    export default{
      props:{
        productName:String,
        productAuthor:String,
        productGenre:String,
        productPublisher:String,
        productPages:Number,
        productIsbn:Number,
        productYear:Number
      }
    }
</script>
<style>
</style>
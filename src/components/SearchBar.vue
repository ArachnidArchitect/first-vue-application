<template lang="">
    <div>
     <input type="text">
     <button id="search-items">Search</button>
    </div>
</template>
<script>
export default {
    data() {
        return {
            sortedArray:[],
            search:''
        }
    },
  props:{
    books:Array
  },
  methods:{
    filter(){

    }
  }  
}
</script>
<style lang="">
    
</style>
<template lang="">
<div>
    {{firstName}}
    {{lastName}}
    {{objectData}}
</div>
</template>
<script>
export default{
    // props:['firstName', 'lastName', 'objectData']
props:{
    firstName:String,
    lastName:String,
    objectData:Object
}
}
</script>
<style scoped>

</style>
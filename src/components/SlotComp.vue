<template lang="">
    <div class="card">
        <h1>
            <slot name="slotTitle">
                404 Title <!--default card template-->
            </slot> 
        
        </h1>
        <h1>
            <slot>
                404 default <!--default card template-->
            </slot>
        
        </h1>
    
    </div>
    </template>
    <script>
    export default{
        // props:['firstName', 'lastName', 'objectData']
    // props:{
    //     firstName:String,
    //     lastName:String,
    //     objectData:Object
    // }
    }
    </script>
    <style scoped>
        div{
        border:3px black solid;
        border-radius: 10%;
        width: 300px;
        margin: auto;
        }
    </style>
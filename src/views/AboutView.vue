<template lang="">
  <div>
    <h1>Conter -> <span>{{counter}}</span></h1>
    <button @click="this.counter++">Increment</button>
    <button @click="decrement()">Decrement</button>
    <button @click="this.counter=0">Reset</button>
    <h2>the value is {{myBool}}</h2>
    <button @click="change()">Change State</button>
  </div>
  <img :src="imgUrl">

  <!-- class styling binding -->
   <h4 :class="{hello:check}">Conditional Rendering</h4>
   <!-- conditional rendering -->
   <h1 v-if="check">The value is true</h1>
   <h1 v-else>The value is true</h1>
   <button @click="change()">change</button>
   <h1 v-show="check">The value contains v-show</h1>
   <ul>
    <!-- <li v-for="sport, index in sports" :key="index">{{sport}}</li> -->
    <li v-for="({message},index) in objects" :key="index">
      {{message}}</li>
   </ul>

   <!-- one way data binding -->
   <h3>{{oneWayText}}</h3>
   <!-- two way data binding -->
    <div>
      <h3>{{twoWayText}}</h3>
      <input type="text" v-model="twoWayText">
    </div>
      


   <info-comp first-name="hehe" last-name="hehehehe"/>
   <info-comp first-name="hehe1"/>
   <info-comp :object-data='singleObject'/>
   <!-- <slot-comp> -->
      <slot-comp>
       <template #template>
        Card Slot
       </template>
       <template #default>
        <img :src="imgUrl">
       </template>
      </slot-comp>
    
    

</template>
<script>
import SlotComp   from "../components/SlotComp.vue";
import InfoComp   from "../components/InfoComp.vue";
export default {
  data(){

    return{
      // all the variables go here
      counter: 0,
      imgUrl: 'https://letsenhance.io/static/8f5e523ee6b2479e26ecc91b9c25261e/1015f/MainAfter.jpg',
      myBool: true,
      check: true,
      sports:['soccer', 'netball', 'volleyball'],
      objects:[
        {message:'Hellow There 1', id:1},
        {message:'Hellow There 2', id:2},
        {message:'Hellow There 3', id:3}
      ],
      singleObject:{
        name: "Taahir",
        surname: "Du Toit"
      },
      oneWayText:"hehehehe",
      twoWayText:"hehe 2.0"
      

    }
  },

  // infoComp data goes here
  components:{
      InfoComp,
      SlotComp
  },
  methods: {
    decrement(){
      this.counter--
    },
    change(){
      if (this.myBool) {
        this.myBool = !true
      }else{
        this.myBool = true
      }
    }
  }
}



</script>
<style scoped>
  h1{
    color:blue;
  }
  img{
    background-color: black;
    border-radius: 100%;
    width: 3em;
    height: 3em;
    box-shadow: 3px 3px 6px rgba(30, 88, 249, 0.525);
  }
</style>
<template>
  <div id="parent">
    <form action="" @submit.prevent="formSubmit">
        <h1>Sign Up form hehe</h1>
        <!-- using v-model to save the properties -->
        <label for="email">Your email:</label>
        <input type="text" id="email" required v-model="email"/>
        
        <label for="password">Password:</label>
        <input type="password" id="password"  required v-model="password"/>
        
        <label for="role">Role:</label>
        <select v-model="role">
            <option value="developer">Web developer</option>
            <option value="designer">Web designer</option>
            <option value="">Select a role</option>
        </select>
      
      <label for="languages">Languages:</label>
      <input type="text" id="languages" v-model="currentLanguages"  @keydown="keyfinder" @keyup.enter.alt="addLanguage()" />
      <button type="submit">submit</button>
      <div v-for="lang,index in languages" :key="index+1">
        <p id="para" @click="deleteLang(lang)">
            {{index+1 }}:{{ lang }}
        </p>
      </div>
      <div class="terms">
        <!-- isn't it insane?, you can use  v-model on a checkbox and when checked, it can register a boolean value as true-->
         <input type="checkbox" required v-model="terms" id="terms">
         <label for="terms">Accept Terms and Conditions</label>
      </div>
<h4>People wanted in your team</h4>
<div>
    <input type="checkbox" value="shawn" id="shawn" v-model="name"    >
    <label for="shawn">Shawn</label>

</div>
<div>
    <input type="checkbox" value="sihlando" id="sihlando" v-model="name"    >
    <label for="sihlando">sihlandlo</label>

</div>
<div>
    <input type="checkbox" value="nthando" id="nthando" v-model="name"    >
    <label for="nthando">Ntando</label>

</div>
    </form>
    <!-- showing stored information in data function -->
    <div>
<p>Email:{{ email }}</p>
<p>Password:{{ password }}</p>
<p>Role:{{ role }}</p>
<p>Terms:{{ terms }}</p>
<p>Names:{{ name }}</p>
<p>Current Language:{{ currentLanguages }}</p>
<p>Languages:{{ languages }}</p>
    </div>
  </div>
</template>
<script>
export default {
    methods: {
        formSubmit(){
            console.log('the page has refreshed');
            this.email = ''
            this.password = ''
            this.terms = false
            this.currentLanguage= ''
            this.role = ""
        },
        keyfinder(event){
            console.log(event)
        },
        deleteLang(lang){
            this.languages = this.languages.filter(item=>item !=lang)
        },addLanguage(){
         this.currentLanguage
        // console.log(this.currentLanguage)
      if(!this.languages.includes(this.currentLanguage)){
         this.languages.push(this.currentLanguage)
        }
    }
        },
   data() {
    return {
        email:'',
        password:'',
        role:'',
        // if you want the default value to be checked then change the boolean to true
        terms: false,
        name:[],
        currentLanguage:'',
        languages:['something', 'nothing'],

    }
   },
   computed:{

    
   }
};
</script>
<style lang=""></style>

<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="container">
      <h2 class="ml-4"> Top puntajes</h2>
      
        
        <div v-for="user in usuarios" :key="user" class="row">
          <User :user="user"/>
        </div>    
      
    </div>
    
  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from '@/components/HelloWorld.vue'
import User from '@/components/User-Items.vue';

export default {
  name: 'Home',
  data(){
    return {
      usuarios: [
        {
          img: 'superman.svg',
          name: 'Fernando',
          points: 123
        },
        {
          img: 'wolverine.svg',
          name: 'Luis',
          points: 432
        },
        {
          img: 'batman.svg',
          name: 'Ariel',
          points: 234
        },
        {
          img: 'lego.svg',
          name: 'Javier',
          points: 212
        }
      ]
    }
   },
  components: {
    User
  }
}
</script>

<template>
  <div class="home">
    <Homepage msg="Welcome to Your Vue.js App"/>
    

  </div>
  <router-view/>
</template>

<script>
// @ is an alias to /src
import Homepage from '@/views/homepage.vue'
import Character from '@/views/character.vue'

export default {
  name: 'Home',
  components: {
    Homepage,
    Character
  }
}
</script>

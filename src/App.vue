<template>
  <div id="app">
    <DrumKit msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import DrumKit from './components/DrumKit.vue'

export default {
  name: 'app',
  components: {
    DrumKit
  },
//   data: function (){
//   return{
//     isActive: true,
//   }
// },
// computed: {
//   selectedButton: function () {
//     return {
//       active: this.isActive 
//     }
//   }
//   },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

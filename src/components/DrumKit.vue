<template>
  <div class="container">
    <button
     v-shortkey="['a']" @shortkey="(soundOff('https://www.kozco.com/tech/piano2.wav'))"
     v-bind:class="selectedButton"
     class="first"
     >
      <span>A</span>
      <span>CLAP</span>
    </button>
    <button 
     v-shortkey="['b']" @shortkey="soundOff('https://www.kozco.com/tech/LRMonoPhase4.wav')"
     v-bind:class="selectedButton"
     @click="removeClass"
     class="second"
    >
      <span>B</span>
      <span>HIHAT</span>
    </button>
    <button 
    v-shortkey="['c']" @shortkey="soundOff('https://www.pacdv.com/sounds/people_sound_effects/applause-1.wav')"
    v-bind:class="selectedButton"
    class="third"
    >
      <span>C</span>
      <span>KICK</span>
    </button>
    <button 
    v-shortkey="['d']" @shortkey="soundOff('https://www.pacdv.com/sounds/people_sound_effects/applause-1.wav')"
    v-bind:class="selectedButton"
    class="fourth"
    >
      <span>D</span>
      <span>OPENHAT</span>
    </button>
  </div>
</template>

<script>
export default {
  name: 'DrumKit',
  props: {
    msg: String
  },
data: function (){
  return{
    isActive: false,
  }
},
computed: {
  selectedButton: function () {
    return {
      selectedButton: this.isActive 
      //an object is always truthy (because it exist)
      //now using the return value of selected button 
    }
  }
  },
  methods: { 
     soundOff(sound){
      alert("Ham Spamwhich")
      var audio = new Audio(sound);
      audio.play();
      this.isActive = !this.isActive
      // this.$set(this.isActive,false,this.isAcvtive) //only used with arrays and dictionaries () 
      }
      //after clicking a button toggling the style back
    }   
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button{
  border: 2px solid green;
  padding:10px;
}
.container{
  border: 2px solid black;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  font-size: 15px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
span{
  display: flex;
  justify-content: center;
  align-items: center; 
}
.selectedButton{
  border: 10px solid coral;
}
</style>

<template>
  <div class="container">
    <button
     v-shortkey="['a']" @shortkey="(soundOff('https://www.kozco.com/tech/piano2.wav','a'))"
     v-bind:class="selectedButtonA"
     class="first"
     >
      <span>A</span>
      <span>CLAP</span>s
    </button>

    <button 
     v-shortkey="['b']" @shortkey="soundOff('https://www.kozco.com/tech/LRMonoPhase4.wav', 'b')"
     v-bind:class="selectedButtonA"
     class="second"
    >
      <span>B</span>
      <span>HIHAT</span>
    </button>

    <button 
    v-shortkey="['c']" @shortkey="soundOff('https://www.pacdv.com/sounds/people_sound_effects/applause-1.wav', 'c')"
    v-bind:class="selectedButtonA"
    class="third"
    >
      <span>C</span>
      <span>KICK</span>
    </button>
    <button 
    v-shortkey="['d']" @shortkey="soundOff('https://www.pacdv.com/sounds/people_sound_effects/applause-1.wav', 'd')"
    v-bind:class="selectedButtonA"
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
    isAActive: false,
    isBActive: false,
    isCActive: false, 
    isDActive: false
  }
},
computed: {
  selectedButton: function () {
    return {
      selectedButtonA: this.isAActive,
      selectedButtonB: this.isBActive, 
      selectedButtonC: this.isCActive,
      selectedButtonD: this.isDActive
      //an object is always truthy (because it exist)
      //now using the return value of selected button 
    }
  }
  },
  methods: { 
     soundOff(sound, key){
      alert("Ham Spamwhich")
      var audio = new Audio(sound);
      audio.play();
      if(key === "a"){
        this.isAActive = !this.isAActive
      }else if(key === "b"){
        this.isBActive = !this.isBActive
      }else if(key === "c"){
        this.isCActive = !this.isCActive
      }else{
        this.isDActive = !this.isDActive
      }
      
      }
      //make is active true for a specific element not in general
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
.selectedButtonA{
  border: 10px solid coral;
}
</style>

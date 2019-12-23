<template>
  <div class="container">
    <div>
      <button
        v-shortkey="['a']" @shortkey="(soundOff('https://www.kozco.com/tech/piano2.wav','a'))"
        v-bind:class="selectedButtonA"
        class="first"
        >
        <span>A</span>
        <span>CLAP</span>
      </button>
 
      <transition class="transition" name="bounce">
       <div class= "starburst" v-if="bounce"></div>
      </transition>
    </div>
    
    
  

    <button 
     v-shortkey="['b']" @shortkey="soundOff('https://www.kozco.com/tech/LRMonoPhase4.wav', 'b')"
     v-bind:class="selectedButtonB"
     class="second"
    >
      <span>B</span>
      <span>HIHAT</span>
    </button>

    <button 
    v-shortkey="['c']" @shortkey="soundOff('https://www.pacdv.com/sounds/people_sound_effects/applause-1.wav', 'c')"
    v-bind:class="selectedButtonC"
    class="third"
    >
      <span>C</span>
      <span>KICK</span>
    </button>
    <button 
    v-shortkey="['d']" @shortkey="soundOff('https://www.pacdv.com/sounds/people_sound_effects/applause-1.wav', 'd')"
    v-bind:class="selectedButtonD"
    class="fourth"
    >
      <span>D</span>
      <span>OPEN</span>
    </button>

    
  </div>
</template>

<script>
// import { timeout } from 'q'
export default {
  name: 'DrumKit',
  props: {
    msg: String
  },
data: () => {
  return { 
    isAActive: false,
    isBActive: false,
    isCActive: false, 
    isDActive: false,
    bounce: false
  }
},
computed: {
  selectedButtonA: function () {
    return {
      selectedButtonA: this.isAActive,
    }
  },
  selectedButtonB: function () {
    return {
      selectedButtonB: this.isBActive,
    }
  },
  selectedButtonC: function () {
    return {
      selectedButtonC: this.isCActive,
    }
  },
  selectedButtonD: function () {
    return {
      selectedButtonD: this.isDActive,
    }
  }
  
  },
  methods: { 
     soundOff(sound, key){
      var audio = new Audio(sound);
      var thing = this
      audio.play();
      if(key === "a"){
        this.isAActive = !this.isAActive
         setTimeout(()=> {
          thing.isAActive = false
          thing.isActive = this.isAActive
          }, 500);
      }else if(key === "b"){
        this.isBActive = !this.isBActive
            setTimeout(()=> {
          thing.isBActive = false
          thing.isBActive = this.isBActive
          }, 500);
      }else if(key === "c"){
        this.isCActive = !this.isCActive
            setTimeout(()=> {
          thing.isCActive = false
          thing.isCActive = this.isCActive
          }, 500);

      }else{
        this.isDActive = !this.isDActive
            setTimeout(()=> {
          thing.isDActive = false
          thing.isDActive = this.isDActive
          }, 500);
      }
         this.bounce = !this.bounce
      }
      //make is active true for a specific element not in general
    }   
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.starburst{
  border: 2px solid purple;
  background-color: blue;
  height: 30px;
  position: absolute;
  width: 40px;
  z-index: 10;
  
}
button{
  width: 10em;
  min-width: 10em;
  height: 6em;
  border-radius: 0.5em;
  border: solid black 1px;
  background-color: #ccc;
  padding: 0.25em;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  z-index: 20;
}
.container{
  border:2px solid black;
  display: flex;
  flex-direction: row;
  background-image: url(https://cdn.pixabay.com/photo/2016/04/15/04/02/water-1330252__340.jpg);
  padding: 50px;
  background-size: cover;
  justify-content: space-between;
  font-size: 15px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  display: flex;
  max-width: 35em;
}
.second{
  padding: 30px;
}
.third{
  padding-left: 34px;
  padding-right: 34px;
}
span{
  display: flex;
  justify-content: center;
  align-items: center; 
}
.selectedButtonA{
  border: 5px solid gold;
  transform: scale(1.1);
  box-shadow: 0 0 10px #ffc600;
}
.selectedButtonB{
  border: 5px solid gold;
  transform: scale(1.1);
  box-shadow: 0 0 10px #ffc600;
}
.selectedButtonC{
  border: 5px solid gold;
  transform: scale(1.1);
  box-shadow: 0 0 10px #ffc600;
}
.selectedButtonD{
  border: 5px solid gold;
  transform: scale(1.1);
  box-shadow: 0 0 10px #ffc600;
}
.bounce-enter-active {
  animation:bounce-in .5s;
}
.bounce-leave-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0% {
    transfrom: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>

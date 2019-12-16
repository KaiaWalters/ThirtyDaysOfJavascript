<template>
  <div class="container">
    <div v-on:click="soundOff">
      <span>A</span>
      <span>CLAP</span>
    </div>
    <div v-on:click="soundOff">
      <span>B</span>
      <span>HIHAT</span>
    </div>
    <div @click="soundOff('https://interactive-examples.mdn.mozilla.net/media/examples/t-rex-roar.mp3')">
      <span>C</span>
      <span>KICK</span>
    </div>
    <div v-on:click="soundOff">
      <span>D</span>
      <span>OPENHAT</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DrumKit',
  props: {
    msg: String
  },
  methods: {
    soundOff(sound){
      alert("tomato")
      var audio = new Audio(sound);
      audio.play();
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div{
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
</style>

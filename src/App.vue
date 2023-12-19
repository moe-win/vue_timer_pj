<template>
  <h1>HOW FAST CAN I CATCH ME</h1>
  <button @click="start" :disabled="heplaying">PLAY</button>
  <div v-if="heplaying">
    <Block :delay="delay" @finishGame="finishGame"/>
  </div>
   <div v-if="end">
    <Result :reactiontime="reactiontime"/>
   </div>
</template>

<script >

import Block from "./components/Block.vue"
import Result from "./components/Result.vue"
export default{
  name: 'App',
  components: {
    Block,
    Result
},
data(){
  return{
    heplaying:false,
    delay:null,
    reactiontime:0,
    end:false
  }
},
methods:{
  start(){
    this.heplaying=true;
    this.delay=2000+Math.random()*5000;   
  },
  finishGame(reactiontime){
     this.reactiontime=reactiontime;
     this.heplaying=false;
     this.end=true;

  }

}
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

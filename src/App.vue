<template>
  <h3>How fast can you catch me ?</h3>
  <button @click="start" :disabled="isplaying">Start</button>
  <div v-if="isplaying">
    <Block :delay="delay" @endgame="endgame"/>
  </div>
  <div v-if="end">
    <Result :score="score"/>
  </div>
</template>

<script>
import Block from "./components/Block.vue"
import Result from "./components/Result.vue"
export default {
  components: { Block, Result },
  data(){
    return{
      isplaying : false,
      delay : null,
      score:0,
      end:false,
    }
  },
  methods:{
    start(){
      this.isplaying = true;
      this.delay = 2000+Math.random()*5000;
    },
    endgame(score){
      this.score = score;
      this.isplaying = false;
      this.end = true;
    }
  }
}
</script>

<style>
 h3{
  text-align: center;
 }
 button{
  display: block;
  margin: auto;
 }
</style>
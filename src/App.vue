<template>
  <h3>How fast can you catch me ?</h3>
  <button @click="start" :disabled="isplaying">Start</button>
  <div v-if="isplaying">
    <Block :delay="delay"/>
  </div>
</template>

<script>
import Block from "./components/Block.vue"
export default {
  components: { Block },
  data(){
    return{
      isplaying : false,
      delay : null,
    }
  },
  methods:{
    start(){
      this.isplaying = true;
      this.delay = 2000+Math.random()*5000;
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
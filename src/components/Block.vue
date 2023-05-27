<template>
    <div v-if="showTime">
    <div class="block">Click Here</div>

    </div>
</template>

<script>
export default {
props : ['delay'],
data(){
    return{
        showTime : false,
    }
},
mounted(){
    setTimeout(() => {
        this.showTime = true;
    }, this.delay);
},
}
</script>

<style>
.block {
    width: 400px;
    height: 300px;
    padding: 10px;
    text-align: center;
    background: greenyellow;
    margin: 30px auto;
}
</style>
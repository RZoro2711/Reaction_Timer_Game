<template>
    <div v-if="showTime">
        <div class="block" @click="stopTimer">Click Here</div>
    </div>
</template>

<script>
export default {
props : ['delay'],
data(){
    return{
        showTime : false,
        score : 0,
        timer : null,
    }
},
mounted(){
    setTimeout(() => {
        this.showTime = true;
        this.startTimer();
    }, this.delay);
},
methods:{
    startTimer(){
        this.timer = setInterval(() => {
            this.score += 50
        }, 50);
    },
    stopTimer(){
        clearInterval(this.timer);
        console.log(this.score);
    }
}
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
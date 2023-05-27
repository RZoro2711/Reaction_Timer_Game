<template>
    <div class="block">Click Here {{ delay }}</div>
</template>

<script>
export default {
props : ['delay']
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
<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        Click me
    </div>
</template>
   
<script>


export default {
    props:['delay'],
    data() { 
        return {
            showBlock: false,
            timer : null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer();
        }, this.delay);
    },

    methods:{
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10;
            }, 10);
        },
        stopTimer(){
            clearInterval(this.timer);
            this.$emit('end',this.reactionTime);
        }
    }
    

}
</script>

<style>
.block {
    width: 300px;
    height: 150px;
    background-color: rgb(32, 189, 110);
    margin: 0 auto;
    margin-top: 100px;
    cursor: pointer;
    text-align: center;
    line-height: 150px;
    font-size: 30px;
    color: white;
    border-radius: 10px;
}
</style>
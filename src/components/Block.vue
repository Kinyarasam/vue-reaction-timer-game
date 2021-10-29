<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        Click Me        
    </div>
</template>

<script>

export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0,
        };
    },
    mounted() {
    //   console.log('component mounted')
      setTimeout(() => {
        this.showBlock = true
        this.startTimer()
        // console.log(this.delay)
      }, this.delay)
    },
   /*  updated() {
      console.log('components updated')
    },
    unmounted() {
      console.log('components unmounted')
    }, */
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            console.log(this.reactionTime)
            this.$emit('end', this.reactionTime);
        },
    }
}
</script>

<style>
body{ 
    background: rgba(200,200,200,0.5)
}
.block {
    width: 400px;
    border-radius: 20px;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    
}
.block:hover{
    box-shadow: 2px 2px 8px #0faf878a;
}
</style>
<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        Click me!
    </div>
</template>

<script>
    export default{
        props: ['delay'],
        data(){
            return{
                showBlock: false,
                timer: null,
                reactionTime: 0
            }
        },
        mounted(){
            //console.log('mounted')    
            setTimeout(() => {
                    this.showBlock = true,this.startTimer()
                }, this.delay)
        },
        updated(){
            //console.log('updated')
        },
        unmounted(){
        //  console.log('unmounted')
        },
        methods:{
            startTimer(){
                this.timer = setInterval(() => {
                    this.reactionTime += 10
                }, 10)
            },
            stopTimer(){
                clearInterval(this.timer)
                this.showBlock = false
                this.$emit('end', this.reactionTime)            
            }
        }
    }
</script>
<style>
.block{
    width: 400px;
    height: 400px;
    background-color: green;
    margin: 10px;
    display: inline-block;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 15px;
    color: white;
    font-size: 1.5rem;
}
</style>
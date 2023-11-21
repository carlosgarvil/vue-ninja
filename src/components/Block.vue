<template>
    <div class="block" v-if="showBlock" @click="">
        Click me!
    </div>
</template>

<script>
    export default{
        props: ['delay'],
        data(){
            return{
                showBlock: false
            }
        },
        mounted(){
            //console.log('mounted')    
            setTimeout(() => {
                    this.showBlock = true
                }, this.delay)
        },
        updated(){
            //console.log('updated')
        },
        unmounted(){
        //  console.log('unmounted')
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
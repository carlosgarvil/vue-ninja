<template>
<p>Results: {{score}}</p>
<p class="rank">{{rank}}</p>
</template>

<script>
    export default{
        props: ['score'],
        data(){
            return{
                rank : null
            }
        },
        mounted(){
            if(this.score < 250){
                this.rank = 'Ninja'
            }else if(this.score < 400){
                this.rank = 'Grasshopper'
            }else{
                this.rank = 'Snail'
            }
        }
        
    }
</script>

<style>
.rank{
    font-size: 2rem;
    font-weight: bold;
    color: #ccc;}
</style>
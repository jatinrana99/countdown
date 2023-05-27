<template>
    <section>
    <div>Time</div>
    <div>
        <p id="time">{{ timer }}</p>
    <Control title="Start" :control="start"/>
    <Control title="Stop" :control="stop"/>
    </div>
    
</section>
</template>

<script>
import Control from './Control.vue'
export default {
    name:`Time`,

    components:{
        Control
    },
    data(){
        return{
           timer:0,
           timerId:0

        }
        
        
    },
    methods:{
        // msg(){
        //     alert("Button Call");
        // },
        start(){
            this.timerId=setInterval(()=>{
                this.timer++;
            },1000);
        },
        stop(){
            clearInterval(this.timerId);
        }
    }
}
</script>

<style scoped>
section{
    background-color: aqua;
    border: 2px solid;
    width: 450px;
    height: 385px;
    border-radius: 50%;
    /* display: flex; */
    display: inline-block;
    /* display: flex; */
    align-items: center; 
    
}

section div{
}
</style>
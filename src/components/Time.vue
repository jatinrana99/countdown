<template>
    <section>
    <div>Time</div>
    <div>
        <!-- <p id="time">{{ timer }}</p> -->
        <p> HRS {{ hr }} : MIN {{ min }} : SEC {{ sec }} : MILS {{ mils }}</p>
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
           timerId:0,
           mils:0,
           hr:0,
           sec:0,
           min:0

        }
        
        
    },
    methods:{
        // msg(){
        //     alert("Button Call");
        // },
        start(){
            this.timerId=setInterval(()=>{
                this.mils++
                if(this.mils==100){
                    this.sec++;
                   this.mils=0;
                }
                if(this.sec==60){
                    this.min++;
                    this.sec=0;
                }
                if(this.min==60){
                    this.hr++;
                    this.min=0;
                }
            },10);
        },
        stop(){
            clearInterval(this.timerId);
        }
    }
}
</script>

<style scoped>
section{
    background-color: rgb(138, 202, 202);
    border: 2px solid;
    width: 450px;
    height: 385px;
    border-radius: 50%;
    /* display: flex; */
    display: inline-block;
    /* display: flex; */
    align-items: center; 
    /* box-shadow: 15px; */
    
}

section div{
    position: relative;
    top: 40%;
}

</style>
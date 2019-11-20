
import { setTimeout } from 'timers';
<template>
    <div class="container">
        <div class="tomato_container">
            <a href=""><img 
            src="../../assets/tomato.svg" 
            alt="Tomato" 
            class="tomato_btn"
            @click.prevent="addTomato"
            ></a>
            <div class="desc">
                <h1 class="title">The Tomato-App</h1>
                <p>You can click on the big tomato above to add a tomato hour. One tomato equals 
                    one hour of productive work. Try to reach as many tomatos as possible each day. </p>
            </div>
        </div>

        <div class="tomato_container">
            <h3>Total of tomato hours: <span class="text_green"> {{tomato}}</span> </h3>
            <div v-if="reached">
            <p class="warning">You have reached 24 hours of work today, maybe you should get some rest!</p>
        </div>
        </div>
        
        <div class="tomato_game">
            <div class="tomato_result" v-for="(tomato, index) in tomatoArray" :key="index">
                <img src="../../assets/tomato.svg" alt="Tomato" class="tomato_img_result">
                
            </div>  
        </div>
        
        
        
    </div>
</template>

<script>
/* eslint-disable no-console */
export default {
  data() {
    return {
      tomato: 0,
      tomatoArray: [],
      reached: false
    };
  },
  methods: {
    addTomato() {
      if (this.tomatoArray.length < 24) {
        this.tomatoArray.push(1);
        this.tomato += 1;
        console.log(this.tomato);
      } else {
        this.reached = true;
        setTimeout(() => {
          this.reached = false;
        }, 4000);
        console.log(this.tomato);
      }
    }
  }
};
</script>
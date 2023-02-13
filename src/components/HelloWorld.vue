<template>
  <h1>{{ msg }}</h1>

<button class="outsideBtn" v-on:click="duplicate">Duplicate</button>
<button class="outsideBtn" v-on:click="background">Background</button>
<button class="outsideBtn" v-on:click="heading">Heading</button>
<button class="outsideBtn" v-on:click="deleter">Delete</button>

<div class="card" v-on:mouseover="hoover">
  <h1 class="title">Baljeet: The IT GOD</h1>

  <img class="Image" src="https://i.redd.it/zckxgrywjpk61.jpg" alt="Baljeet">
  
<div class="details">
  <details>
    <summary class="haxbtn">Details</summary>
    <p class="description pScale">Baljeet is here to fix all of your IT problems</p>
  </details>

  </div>
</div>

  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Documentation
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p>

  <button type="button" @click="state.count++">count is: {{ state.count }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
</script>

<script>
export default {
  methods: {
    hoover() {
      document.querySelectorAll(".card").forEach((item) => {
        if(!item.classList.contains("hoverCard")){
          item.classList.add("hoverCard");
          console.log(item);
        }
        else{
          item.classList.remove("hoverCard");
          console.log(item);
        }
      });
    },
    
    duplicate() {
      const cloneCard = document.querySelector(".card").cloneNode(true);
      document.body.appendChild(cloneCard);
      console.log(cloneCard);    
    },
    background() {
      document.querySelectorAll(".card").forEach((item) => {
        if(!item.classList.contains("basic")){
          item.classList.add("basic");
          console.log(item);
        }
        else{
          item.classList.remove("basic");
          console.log(item);
        }
      });
    },
    heading() {
      document.querySelectorAll(".title").forEach((item) => {   
        if(item.innerHTML=="something else"){
          item.innerHTML="Baljeet: The IT GOD";
        }
        else{
          item.innerHTML="something else";
        }
      });
    },
    //Kinda borked rn
    deleter(){
      document.querySelector(".card:last-child").remove();
      console.log(card);
    }
  }
}
</script>

<style scoped>
a {
  color: #42b983;
}
</style>

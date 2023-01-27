<template>
  <div>
    <Navbartop/>
    
  <div class="py-10 px-8 mx-auto rounded mt-16 border-8 ring-8 ring-neutral-50 border-neutral-100 max-w-4xl">
    <h1 class="text-3xl font-bold text-neutral-400">Accordeur de Guitare</h1>
    <div class="flex items-end">
      <div>
        <Guitar @click="(value) => onClick(value)"/>
      </div>
      <div class="space-y-10 w-full">
        <Accordeur class="max-w-[272px]" :rightValue="activeFrequency" />
        <div class="border-4 rounded border-neutral-500 pt-8 px-4 w-full">
          <div class="text-xl uppercase font-bold text-neutral-700">accordage</div>
          <div class="flex flex-col items-start mt-4 pb-2">
            <button
              v-for="[name, accordage] in Object.entries(accordages)"
              :key="name"
              class="text-lg text-neutral-500 hover:text-neutral-700 hover:text-xl"
            >
              {{ name }} : {{ accordage }}
            </button>
          </div>
        </div>
      </div>
      
    </div>
    
  </div>
  <Footers/>
</div>
  
</template>

<script>
import Accordeur from "../components/Accordeur";
import GuitarView from "../components/GuitarView"
import frequencies from '../content/frequency.js'
import Navbartop from "../components/navbartop";
import Footers from "../components/footers.vue"




import accordages from "../content/accordage"


export default {
  components: {
    Accordeur,
    GuitarView,
    Navbartop,
    Footers,
    
  },

  data() {
    return {
      frequencies,
      accordages,
      imageUrl: 'https://img.freepik.com/vecteurs-libre/vecteur-fond-motif-geometrique-blanc-or_53876-140726.jpg?t=st=1674806222~exp=1674806822~hmac=586183d650f633ee1b5ea0c14306eeff5e1c0ee8e3181ae13af5fbe1469ad9cf',
      activeFrequency: frequencies[0].frequency,
    }
  },

  methods: {
    onClick(value) {

    }
  }
}
</script>

<style>
html { 
  background: url(https://img.freepik.com/vecteurs-libre/vecteur-fond-motif-geometrique-blanc-or_53876-140726.jpg?t=st=1674806222~exp=1674806822~hmac=586183d650f633ee1b5ea0c14306eeff5e1c0ee8e3181ae13af5fbe1469ad9cf) no-repeat center center fixed; 
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

.ring-neutral-50 {
    --tw-ring-opacity: 1;
    --tw-ring-color: rgb(250 250 250 / var(--tw-ring-opacity));
    
    margin-top: 300px;
    background-color: white;
}

.text-neutral-400 {
    --tw-text-opacity: 1;
    color: rgb(163 163 163 / var(--tw-text-opacity));
    text-align: center;
    margin-top: -100px;
}
</style>
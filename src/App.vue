<script setup>
import { ref } from "vue" 

let tabla = ref(4)

let tablaInput

let operacionProhibida = ref(false)
let valorMuyAlto = ref(false)

const calcular = () => {
operacionProhibida.value = false
tablaInput = +tablaInput

if(tablaInput == 0){
  operacionProhibida.value = true
}

if(tablaInput < 0){
  tablaInput = tablaInput * -1
}

if(tablaInput >= 1 && tablaInput <=100){
  tabla.value = tablaInput  
}else{
  valorMuyAlto.value = true
}


}

</script>

<template>
  <input type="text" v-model="tablaInput">
  <button @click="calcular">Calcular</button>
  <br />

  <p v-show="operacionProhibida == true">OperacionProhibida</p>
  <p v-show="valorMuyAlto ==true">Valor muy Alto</p>

  {{tabla}} x 1 = {{ tabla * 1 }} <br />
  {{tabla}} x 2 = {{ tabla * 2 }} <br />
  {{tabla}} x 3 = {{ tabla * 3 }} <br />
  {{tabla}} x 4 = {{ tabla * 4 }} <br />
  {{tabla}} x 5 = {{ tabla * 5 }} <br />
  {{tabla}} x 6 = {{ tabla * 6 }} <br />
  {{tabla}} x 7 = {{ tabla * 7 }} <br />
  {{tabla}} x 8 = {{ tabla * 8 }} <br />
  {{tabla}} x 9 = {{ tabla * 9 }} <br />
  {{tabla}} x 10 = {{ tabla * 10 }} <br />
  </template>

<style scope>
</style>
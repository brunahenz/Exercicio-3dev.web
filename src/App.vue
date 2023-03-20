<script setup>
import { ref, computed} from 'vue'
const contador = ref (10)
const contador2 = ref (10)
const ativo = ref(true)
const soma = computed(() => {
    return contador.value + contador2.value
})
const parImpar = computed(() => {
    return (contador.value + contador2.value) % 2 === 0 
})

function incrementar (){
  contador.value++
}

function incrementar2(){
  contador2.value++
}

function decrementar(){
  if (contador.value > 0)
  contador.value--
}

function decrementar2(){
  if (contador2.value > 0)
  contador2.value--
}
</script>

<template>
  <button @click="incrementar">+</button>
  <button @click="decrementar">-</button>
  <button @click="incrementar2">+</button>
  <button @click="decrementar2">-</button>

  <p>Valor do contador: {{  contador }}</p>
  <p>Valor do contador: {{  contador2 }}</p>
  <div v-if="soma > 10" >A soma é maior que 10</div>
      <div v-else-if="soma < 10" >A soma é menor que 10</div>
      <div v-else>O contador é 10</div>
      <hr>
      <div v-if="parImpar">É par</div>
      <div v-else>É impar</div>
    <div><p>Verdadeiro ou Falso: {{ ativo }}</p></div>
</template>

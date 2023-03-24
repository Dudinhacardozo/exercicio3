<script setup>
import { ref , computed } from 'vue'
const contador1 = ref(0)
const contador2 = ref(0)
const mostrar = ref (true)
const soma = computed(() => contador1.value + contador2.value)
</script>
<template>
<button class="btn btn-dark" @click="mostrar = !mostrar">mostrar / esconder</button>
<div v-if="mostrar">
<div>
  <button class="btn btn-primary" @click="contador1--">-</button>
  <span class="display-6">{{ contador1 }}</span>
  <button class="btn btn-primary" @click=" contador1++">+</button>
</div>
<button class="btn btn-primary" @click="contador2--">-</button>
<span class="display-6">{{ contador2 }}</span>
<button class="btn btn-primary" @click="contador2++">+</button>
<div>
  <p class="display-6">a soma é{{ soma }}</p>
  <p v-if="soma > 10" class="display-6">Soma é maior que 10</p>
  <p v-else class="display-6">Soma é menor ou igual a 10</p>
  </div>
  <hr/>
</div>
</template>

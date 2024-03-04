<script setup>
import { computed, ref } from "vue";
const contador = ref(0);
const contador2 = ref(0);
const somaDosValores = computed(() => {
 if (contador + contador2 > 10) {
    return contador + contador2;
  }
});
const diferencaDosValores = computed(() => {
  if (contador + contador2 < 10) {
    return contador + contador2;
  }
});
function incrementar() {
  contador.value++;
}
function decrementar() {
  if (contador.value > 0) {
    contador.value--;
  }
}
function reiniciar() {
  contador.value = 0;
}
function adicionar() {
  contador2.value++;
}
function diminuir() {
  if (contador2.value > 0) {
    contador.value--;
  }
}
function zerar() {
  contador2.value = 0;
}
</script>

<template>
  <div class="info">
    <button @click="incrementar">+</button>
    <button @click="decrementar">-</button>
    <button @click="reiniciar">zerar</button>
    <p>Valor do contador: {{ contador }}</p>
    <button @click="adicionar">+</button>
    <button @click="diminuir">-</button>
    <button @click="zerar">zerar</button>
    <p>Valor do contador: {{ contador2 }}</p>
  </div>
  <div></div>
</template>
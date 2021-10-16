<template>
  <div class="teclado">
    <button
      class="teclado-botao"
      v-for="(letra, id) in 'abcdefghijklmnopqrstuvwxyz'"
      :key="id"
      :disable="verificaLetra(letra)"
      @click="jogar(letra)"
    >
      {{ letra }}
    </button>
  </div>
</template>

<script>
export default {
  name: "Teclado",
  props: {
    letras: Array,
    verificaLetra: Function,
    jogar:Function
  },
  data() {
    return {};
  },
  components: {},
};
</script>

<style>
.teclado{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  max-width: 80%;
  margin-top: 20px;
}
.teclado-botao{
  margin: 5px;
  text-transform: uppercase;
}
</style>
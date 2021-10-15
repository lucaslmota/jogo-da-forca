<template>
  <div id="app">
    <h1>Jogo da forca</h1>

    <section v-if="tela === 'inicio'" id="inicio">
      <Formulario v-if="etapa === 'palavra'"
        title="Defina a palavra"
        button="Próximo" 
        :action ="setPalavra"
        />

        <Formulario v-if="etapa === 'dica'"
        title="Defina a dica"
        button="Iniciar Jogo" 
        :action ="setDica"/>


    </section>

    <section v-if="tela === 'jogo'" id="jogo">
      <Jogo 
      :erros = "erros"
      />
    </section>

  </div>
</template>

<script>
import "./css/global.css";

import Formulario from './components/Formulario.vue';
import Jogo from './components/Jogo.vue'

export default {
  name: "App",
  data() {
    return {
      tela: "inicio",
      etapa: 'palavra',
      palavra:'',
      dica:'',
      erros: 3
    };
  },
  components: {Formulario, Jogo},

  methods:{
    setPalavra(palavra){
      this.palavra = palavra;
      this.etapa = 'dica'
    },

    setDica(dica){
      this.dica = dica;
      this.tela = 'jogo';
      this.etapa = 'jogo'
    }
  },
};
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>

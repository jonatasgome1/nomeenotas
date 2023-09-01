<template>

  <div id="app">
    <NomeENotas @adicionar="adicionarNomeENotas" />
    <ListaNomesENotas :itens="nomesENotas" />
  </div>
</template>

<script>

import NomeENotas from "./components/NomeENotas.vue";
import ListaNomesENotas from "./components/ListaNomesENotas.vue";

export default {
  components: {
    NomeENotas,
    ListaNomesENotas,
  },
  data() {
    return {
      nomesENotas: [],
    };
  },
  methods: {
    adicionarNomeENotas(dados) {
      this.nomesENotas.push(dados);
    },
  },
};
</script>
<style>

*{
  font-family: Arial, Helvetica, sans-serif;
}
</style>

<template>
    <div>
      
      <h2>Insira o Nome e as Notas</h2>
      <form @submit.prevent="adicionarNomeENotas">
        <label for="nome">Nome:</label>
        <input type="text" id="nome" v-model="nome" required />
  
        <label for="nota">Nota:</label>
        <input type="number" id="nota" v-model="nota" required />
  
        <button type="submit">Adicionar</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        nome: "",
        nota: null,
      };
    },
    methods: {
      adicionarNomeENotas() {
        if (this.nome.trim() === "" || this.nota === null) {
          return; // Evitar adicionar entradas vazias
        }
  
        this.$emit("adicionar", { nome: this.nome, nota: this.nota });
  
        // Limpar os campos após adicionar
        this.nome = "";
        this.nota = null;
      },
    },
  };
  </script>
  
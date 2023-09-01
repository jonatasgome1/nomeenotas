<template>
    <div>
      <h2>Lista de Nomes e Notas</h2>
  
      <h3>Reprovados</h3>
      <ul>
        <li v-for="(item, index) in reprovados" :key="index">
          <strong>{{ item.nome }}:</strong> {{ item.nota }}
        </li>
      </ul>
      
      <h3>Aprovados</h3>
      <ul>
        <li v-for="(item, index) in aprovados" :key="index">
          <strong>{{ item.nome }}:</strong> {{ item.nota }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      itens: {
        type: Array,
        required: true,
      },
    },
    computed: {
      reprovados() {
        return this.itens.filter(item => item.nota < 7);
      },
      aprovados() {
        return this.itens.filter(item => item.nota >= 7);
      },
    },
  };
  </script>
  
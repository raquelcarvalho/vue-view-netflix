<template>
  <div class="contain">
    <Categoria v-for="categoria in categorias" v-bind:key="categoria.id" v-bind:titulo="categoria.titulo" v-bind:filmes="categoria.filmes" />
  </div>
</template>

<script>

import Categoria from '../components/Categoria'

export default {
  name: 'Home',
  components: {
    Categoria
  },
  data () {
    return {
      categorias: []
    }
  },
  created () {
    this.$http.get('http://localhost:3000/categorias').then(response => {
      this.categorias = response.body
    }, response => {
      console.log(response)
    })
  }
}
</script>

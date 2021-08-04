<template>
  <div class="container-fluid mt-5">
    <div class="row">
      <div class="col-6 col-xl-4 offset-xl-2 text-initial">
        <input id="book-search-element" type="search" name="" placeholder="Procure por um livro">
      </div>
      <div class="col-6 col-xl-4 filtro">
        <select id="book-filter-element" name="Filtros" placeholder="Filtros">
          <!-- <option :value="null">
            Filtros
          </option> -->
          <option v-for="tipo in filtros" :key="tipo.id" :value="tipo.id">
            {{ tipo.tipoFiltro }}
          </option>
        </select>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      filtros: [
        {
          id: 0,
          tipoFiltro: 'Melhores Avaliados'
        },
        {
          id: 1,
          tipoFiltro: 'Em Estoque'
        },
        {
          id: 2,
          tipoFiltro: 'Ordem Alfabética'
        },
        {
          id: 3,
          tipoFiltro: 'Livros Curtidos'
        },
        {
          id: 4,
          tipoFiltro: 'Por Categoria'
        }
      ]
    }
  }
}
</script>

<style scoped>
    .filtro {text-align: right;}
</style>

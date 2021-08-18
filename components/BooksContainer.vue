<template>
  <div class="books-container">
    <div class="container-fluid mt-5">
      <div class="row">
        <div class="col-6 col-xl-4 offset-xl-2 d-grid">
          <input id="book-search-element" type="search" name="" placeholder="Procure por um livro" class="shadow-box1 input-padrao book-search">
          <div class="total-livros">
            Total: {{ totalLivros }}
          </div>
        </div>
        <div class="col-6 col-xl-4 filtro">
          <select id="book-filter-element" name="Filtros" placeholder="Filtros" class="input-padrao shadow-box1">
            <!-- <option :value="null">
            Filtros
          </option> -->
            <option v-for="tipo in filtros" :key="tipo.id" :value="tipo.id">
              {{ tipo.tipoFiltro }}
            </option>
          </select>
        </div>
      </div>
      <div class="row">
        <Book
          v-for="(book, index) in books"
          :key="book.id"
          :book-index="(index)"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      books: 8,
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
  },
  computed: {
    totalLivros () {
      return this.books
    }
  }
}
</script>

<style scoped>
    .filtro {text-align: right;}
    .book-search {width: 50%;}
    .total-livros {
      position: relative;
      top: 20px;
      color: gray;
      font-size: 1.2rem;
    }
</style>

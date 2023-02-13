<template>
 <div id="app" class="app">
  <header class="app__heading">
    <h1>Books<span>.app</span></h1>
  </header>
  <books-list
  :booksAPI="booksAPI" />
  <books-length-msg
  :booksAPI="booksAPI" />
  <!-- <books-form
  @add="addBook" />
  <books-summary
  :books="books" /> -->
 </div>
</template>

<script>
import axios from 'axios'

import BooksList from './components/BooksList'
import BooksLengthMsg from './components/BooksLengthMsg'
// import BooksForm from './components/BooksForm.vue'
// import BooksSummary from './components/BooksSummary.vue'

export default {
  name: 'App',
  data: () => ({
    booksAPI: []
  }),
  // methods: {
  // removeBook (index) {
  //   this.books.splice(index, 1)
  // },
  // addBook (book) {
  //   this.books.push({ ...book })
  // }
  // },
  created () {
    axios.get('https://wolnelektury.pl/api/books')
      .then(res => console.log(this.booksAPI = res.data.slice(0, 3)))
      .catch(err => console.error(err))
  },
  components: {
    BooksList,
    BooksLengthMsg
    // BooksForm,
    // BooksSummary
  }
}
</script>

<style lang="scss" scoped>
.app {
  width: 100%;
  max-width: 1000px;
  padding: 2rem;
  margin: 0 auto;

  &__heading {
    font-size: 3rem;
    text-align: center;
    span {
      color: #5a58da;
    }
  }
}
</style>

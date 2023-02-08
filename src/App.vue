<template>
 <div id="app">
  <header>
    <h1>Books<span>.app</span></h1>
  </header>
  <books-list
  @remove="removeBook"
  :books="books" />
  <books-length-msg
  :books="books" />
  <books-form
  @add="addBook" />
  <books-summary
  :books="books" />
 </div>
</template>

<script>
import BooksList from './components/BooksList'
import BooksLengthMsg from './components/BooksLengthMsg'
import BooksForm from './components/BooksForm.vue'
import BooksSummary from './components/BooksSummary.vue'

export default {
  name: 'App',
  data: () => ({
    books: [
      {
        title: 'The Catcher in the Rye',
        price: 20
      },
      {
        title: 'Of Mice and Men',
        price: 18
      }
    ]
  }),
  methods: {
    removeBook (index) {
      this.books.splice(index, 1)
    },
    addBook (book) {
      this.books.push({ ...book })
    }
  },
  components: {
    BooksList,
    BooksLengthMsg,
    BooksForm,
    BooksSummary
  }
}
</script>

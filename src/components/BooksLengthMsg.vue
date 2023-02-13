<template>
    <div>
        <p v-if="booksAPI.length > 5">{{ booksAPI.length }}</p>
        <p v-else-if="booksAPI.length <= 5 && booksAPI.length > 1">Not too many of them…</p>
        <p v-else-if="booksAPI.length === 1">One single book!</p>
        <p v-else>Go get some books!</p>
  </div>
</template>

<script>
export default {
  name: 'BooksLengthMsg',
  props: {
    booksAPI: {
      type: Array
    }
  }
}
</script>

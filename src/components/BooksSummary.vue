<template>
    <div class="booksInfo">
        <span>Books amount: {{ books.length }}</span>
    </div>
    <div class="booksInfo">
        <span>Books price: {{ summary }} </span>
    </div>
</template>

<script>
export default {
  name: 'BooksSummary',
  props: {
    books: {
      type: Array,
      required: true
    }
  },
  computed: {
    summary () {
      return this.books.reduce((acc, book) => acc + book.price, 0)
    }
  }
}
</script>

<style lang="scss" scoped>
    .booksInfo {
        margin-top: 10px;
    }
</style>

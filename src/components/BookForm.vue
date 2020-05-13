<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" placeholder="Book Title" />
    <input v-model="bookData.bookAuthor" type="text" name="author" placeholder="Book Author" />
    <div>
      <input type="checkbox" name="finishedReading" v-model="bookData.finishedReading" />
      <label for="finishedReading">Finished Reading</label>
      <input type="radio" name="ownership" v-model="bookData.ownership" value="borrowed" />
      <label for="borrowed">borrowed</label>
      <input type="radio" name="ownership" v-model="bookData.ownership" value="bought" />
      <label for="bought">bought</label>
    </div>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>

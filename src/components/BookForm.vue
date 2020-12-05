<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <div>
        <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
        <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    </div>
    <div>
        <label for="finishedReading">
            Finished Reading
        </label>
        <input type="checkbox" name="finishedReading" id="finishedReading" v-model="bookData.finishedReading">
    </div>
    <div>
        <label for="bought">
            bought
        </label>
        <input type="radio" name="ownership" value="bought" id="bought" v-model="bookData.ownership">
        <label for="borrowed">
            borrowed
        </label>
        <input type="radio" name="ownership" value="borrowed" id="borrowed" v-model="bookData.ownership">
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

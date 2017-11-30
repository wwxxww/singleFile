<template>
  <div class="home">
      <home-header></home-header>
      <ul>
          <li is="list" v-for="book in books" :key="book.id" :book="book"></li>
      </ul>
  </div>
</template>

<script>
import HomeHeader from "@/components/HomeHeader.vue";
import List from "@/components/List.vue";
import axios from "axios";
export default {
  name: "Home",
  methods: {
    // 获取books
    getBooks() {
        // localhost:8080/api/getbooks  => localhost:7000/getbooks
      axios
        .get("/api/getbooks")
        .then(function(res) {
          //   console.log(res);
          this.books = res.data.books;
        }.bind(this))
        .catch(function(e) {
          console.log(e);
        });
    }
  },
  mounted() {
    this.getBooks();
  },
  data() {
    return {
      books: []
    };
  },
  components: {
    "home-header": HomeHeader,
    list: List
  }
};
</script>

<style scoped>
ul {
  max-width: 640px;
  margin: 0 auto;
  margin-top: 8px;
}
</style>


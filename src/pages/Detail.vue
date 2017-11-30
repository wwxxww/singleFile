<template>
  <div class="detail">
      <detail-header></detail-header>
      <img :src="book.img" alt="">
      <p>{{book.desc}}</p>
  </div>
</template>

<script>
import DetailHeader from "@/components/DetailHeader.vue";
import axios from "axios";
import $ from "jquery";
export default { 
  name: "Detail",
  data() {
    return {
      book: {}
    };
  },
  methods: {
    getBook(id) {
      // 1. 使用axios请求数据
      // axios
      //   .get("/api/getbook/" + id)
      //   .then(function(res) {
      //     this.book = res.data.book;
      //   }.bind(this))
      //   .catch(function(err) {
      //     console.log(err);
      //   });
      // 2. 通过vue-resource获取数据
      // this.$http.get("/api/getbook/" + id).then(
      //   function(res) {
      //     this.book = res.body.book;
      //   },
      //   function(err) {
      //     console.log(err);
      //   }
      // );
      // 3. 通过jquery获取数据
      $.get("/api/getbook/" + id, function(res) {
        console.log(res);
        this.book = res.book;
      }.bind(this));
    }
  },
  mounted() {
    var id = 1;
    if (this.$route.params.id) {
      id = this.$route.params.id;
    }
    this.getBook(id);
  },
  components: {
    "detail-header": DetailHeader
  }
};
</script>

<style scoped>
.detail {
  padding: 0.24rem;
  font-size: 12px;
}
img {
  display: block;
  max-width: 640px;
  margin: 0 auto 0.2rem;
}
p {
  max-width: 640px;
  margin: 0 auto;
  font-size: 14px;
  line-height: 0.5rem;
  text-align: justify;
  padding-bottom: 0.24rem;
}
</style>
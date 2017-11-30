<template>
    <li class="sec_li">
        <router-link :to="'/detail/' + book.id" class="lp_li_a">
            <div class="lp_li_imgWrap">
                <img :src="book.img" alt="">
            </div>
            <p class="lp_li_name">{{ book.title }}</p>
            <p class="lp_li_price">￥{{ book.price }}元</p>
        </router-link>
    </li>
</template> 
 
<script>
export default {
  props: ["book"],
  name: "List"
};
</script>

<style scoped>
.sec_li {
  float: left;
  width: 50%;
  margin-bottom: 0.1rem;
}
.lp_li_a {
  display: block;
  padding: 0.3rem 0;
  margin: 0 0;
  border: 1px solid #80ccd6;
  text-align: center;
  background: #fff;
}
.lp_li_imgWrap {
  padding: 0.24rem 0;
}
.lp_li_imgWrap > img {
  width: auto;
  height: 2.3rem;
}
.lp_li_name {
  height: 0.5rem;
  line-height: 0.5rem;
  font-size: 16px;
  color: #333;
}
.lp_li_price {
  height: 0.5rem;
  line-height: 0.5rem;
  font-size: 16px;
  color: #fb3b3b;
}
</style>
<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: "app"
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
html,
body {
  background: #eee;
}
ul,
li {
  list-style: none;
}
a {
  text-decoration: none;
}
img {
  vertical-align: middle;
}
</style>

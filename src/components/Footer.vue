<template>
  <footer>
    <p>Copyright by Nazmul Haque &copy;2021</p>
    <router-link to="/about">About</router-link>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
a {
  color: #333;
}

footer {
  margin-top: 20px;
  text-align: center;
}
</style>

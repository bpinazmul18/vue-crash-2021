<template>
  <footer>
    <p :class="aboutPage ? '' : 'text-center'">
      Copyright by Nazmul Haque &copy;2021
    </p>
    <router-link v-show="aboutPage" to="/about">About</router-link>
  </footer>
</template>

<script>
export default {
  name: "Footer",
  computed: {
    aboutPage() {
      if (this.$route.path === "/about") {
        return false;
      } else {
        return true;
      }
    },
  },
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
.text-center {
  text-align: left;
}
</style>

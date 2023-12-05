<script >
  import { store } from "./store.js"
  import AppHeader from "./components/AppHeader.vue"
  import AppBody from "./components/AppBody.vue"
  import AppFooter from "./components/AppFooter.vue"

  export default {
    components: { AppHeader, AppBody, AppFooter },
    data() {
      return {
        store,
      }
    },
  }
</script>

<template>
  <p> test </p>
  <AppHeader />
  <AppBody />
  <AppFooter />
</template>

<style lang="scss">
@use "./style/general.scss";
@import "@fortawesome/fontawesome-free/css/all.css";

</style>

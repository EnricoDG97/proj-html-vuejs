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
  <div class="bg">
    <AppHeader />
    <AppBody />
    <AppFooter />
  </div>
</template>

<style lang="scss">
@use "./style/partials/mixins" as *;
@use "./style/partials/variables" as *;
@use "./style/general.scss";
@import "@fortawesome/fontawesome-free/css/all.css";

.bg {
  background-color: $main-bg-color;
}
</style>

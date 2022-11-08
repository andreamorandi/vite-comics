<script>
import AppHeader from "./components/AppHeader.vue";
import AppContent from "./components/AppContent.vue";
import AppBanner from "./components/AppBanner.vue";
import AppFooter from "./components/AppFooter.vue";

export default {
  components: {
    AppHeader,
    AppContent,
    AppBanner,
    AppFooter
  }
}
</script>

<template>
  <AppHeader />
  <AppContent />
  <AppBanner />
  <AppFooter />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>
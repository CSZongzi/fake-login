<script lang="ts" setup>
import Content from '@/layout/Content.vue';
import Footer from '@/layout/Footer.vue';
import TopNav from '@/layout/TopNav.vue';
</script>

<template>
  <TopNav />
  <Content />
  <Footer />
</template>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
}

body {
  min-height: 100vh;
  font-family: system-ui, sans-serif;
  color: #111;
}
</style>

<template>
  <section class="w-full pb-12 antialiased">
    <div class="mx-auto max-w-8xl">
      <TheHeader />
      <Nuxt />
    </div>
  </section>
</template>

<script>
import TheHeader from "../components/TheHeader.vue";

export default {
  component: {
    TheHeader,
  },
};
</script>

<style scoped>

</style>

<template>
  <div>
    <!-- {{ el }} -->
    <nuxt-content :document="el" class="prose" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const el = await $content(params.slug).fetch();
    return { el };
  }
};
</script>

<style></style>

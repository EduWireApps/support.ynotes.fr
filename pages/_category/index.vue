<template>
  <Container class="py-12">
    <div class="text-center mb-10">
      <h1>{{ category.name }}</h1>
      <p>{{ category.description }}</p>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-2">
      <div v-for="(el, index) in articles" :key="index">
        <nuxt-link
          :to="el.path"
          class="block p-4 transition-all transform bg-white shadow rounded-2xl hover:shadow-xl hover:-translate-y-1 h-full"
        >
          <div class="text-2xl font-semibold text-gray-800 mb-3">
            {{ el.title }}
          </div>
          <div class="text-lg text-justify">{{ el.description }}</div>
        </nuxt-link>
      </div>
    </div>
  </Container>
</template>

<script>
export default {
  head() {
    return {
      title: "CATEGORY",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "DESCRIPTION"
        }
      ]
    };
  },
  async asyncData({ $content, params }) {
    let content = require("@/assets/content/content.json"),
      category = content.categories.find(c => c.folder == params.category);
    const articles = await $content({ deep: true })
      .where({ dir: { $eq: "/" + category.folder } })
      .fetch();
    return {
      category,
      articles
    };
  }
};
</script>

<style></style>

<template>
  <Container class="py-12">
    <nuxt-link
      to="/"
      class="inline-flex items-center px-3 py-1 mb-5 text-base font-semibold text-white transition duration-150 ease-in-out rounded-md focus:outline-none bg-space-400 hover:bg-space-300"
      ><svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
        class="w-4 h-4 mr-2"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M10 19l-7-7m0 0l7-7m-7 7h18"
        />
      </svg>
      Retour
    </nuxt-link>
    <div class="text-center mb-10">
      <h1 class="text-5xl leading-8 font-extrabold tracking-tight text-gray-900 lg:text-6xl mb-4">{{ category.name }}</h1>
      <p class="max-w-3xl text-xl text-gray-500 lg:mx-auto">{{ category.description }}</p>
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
      title: this.category.name,
      meta: [
        {
          hid: "description",
          name: "description",
          content: this.category.description
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
    console.log(articles)
    return {
      category,
      articles
    };
  }
};
</script>

<style></style>

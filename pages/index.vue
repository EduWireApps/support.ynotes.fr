<template>
  <div>
    <div
      class="relative flex items-center justify-center bg-gradient-to-r from-space-400 to-space-500 h-72"
    >
      <!-- <div
      class="relative flex items-center justify-center bg-center bg-cover h-72"
      :style="
        'background-image: url(' + require('~/assets/images/hero.png') + ')'
      "
    > -->
      <!-- <div class="absolute inset-0 z-10">
        <div class="absolute inset-0 bg-black opacity-60"></div>
      </div> -->
      <div class="z-10 max-w-full px-4 w-224">
        <h1
          class="mb-4 text-3xl font-bold text-center text-white sm:text-4xl lg:text-6xl md:mb-8 xyz-nested "
        >
          Centre d'aide
        </h1>
        <SearchBar />
      </div>
    </div>
    <Container class="py-12">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-2">
        <div v-for="(el, index) in content.categories" :key="index">
          <nuxt-link
            :to="el.folder"
            class="block p-4 transition-all transform bg-white shadow rounded-2xl hover:shadow-xl hover:-translate-y-1 h-full"
          >
            <div class="text-2xl font-semibold text-gray-800 mb-3">
              {{ el.name }}
            </div>
            <div class="text-lg text-justify">{{ el.description }}</div>
          </nuxt-link>
        </div>
      </div>
    </Container>
  </div>
</template>

<script>
import content from "@/assets/content/content.json";

export default {
  data() {
    return {
      content: content
    };
  },
  // async asyncData({ $content }) {
  //   console.log(require("@/assets/content/content.json"))
  //   const elements = await $content({ deep: true })
  //     .only(["title", "path", "description"])
  //     .sortBy("createdAt", "asc")
  //     .fetch();
  //   return { elements };
  // }
};
</script>

<style></style>

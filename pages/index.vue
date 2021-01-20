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
          class="mb-4 text-3xl font-bold text-center text-white sm:text-4xl lg:text-6xl md:mb-8 xyz-nested"
          v-html="indexJson.title"
        ></h1>
        <SearchBar />
      </div>
    </div>
    <Container class="py-12">
      <div class="py-8 text-center">
        <h2
          class="mb-3 text-3xl font-semibold font-display sm:text-4xl xl:text-5xl"
          v-html="indexJson.cta.title"
        ></h2>
        <p
          class="mx-auto text-lg text-gray-700 sm:text-xl sm:max-w-xl xl:mt-4 xl:text-2xl xl:max-w-2xl"
          v-html="indexJson.cta.content"
        ></p>
        <p
          class="mx-auto text-lg text-gray-700 sm:text-xl sm:max-w-xl xl:mt-4 xl:max-w-2xl"
        >
          <span v-html="indexJson.contact.content"></span>
          <a
            :href="indexJson.contact.link.url"
            target="_blank"
            rel="noopener noreferrer"
            v-html="indexJson.contact.link.text"
            class="text-space-300 hover:text-space-400"
          ></a>
        </p>
      </div>
      <div class="grid grid-cols-1 gap-2 md:grid-cols-2 lg:grid-cols-3">
        <div v-for="(el, index) in content.categories" :key="index">
          <nuxt-link
            :to="el.folder"
            class="block h-full p-4 transition-all transform bg-white shadow rounded-2xl hover:shadow-xl hover:-translate-y-1"
          >
            <div class="mb-3 text-2xl font-semibold text-gray-800">
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
import indexJson from "@/assets/content/index.json";
import content from "@/assets/content/content.json";

export default {
  data() {
    return {
      content: content,
      indexJson: indexJson
    };
  }
};
</script>

<style></style>

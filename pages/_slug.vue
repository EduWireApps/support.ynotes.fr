<template>
  <Container class="py-12 sm:max-w-3xl md:max-w-4xl lg:max-w-6xl">
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
    <div
      class="mx-auto prose text-justify sm:max-w-3xl md:max-w-4xl lg:max-w-6xl md:prose-lg lg:prose-xl "
    >
      <h1>
        {{ el.title }}
      </h1>
      <nuxt-content :document="el" />
    </div>
  </Container>
</template>

<script>
export default {
  head() {
    return {
      title: this.el.title,
      meta: [
        {
          hid: "description",
          name: "description",
          content: this.el.description
        }
      ]
    };
  },
  async asyncData({ $content, params }) {
    const el = await $content(params.slug).fetch();
    return { el };
  }
};
</script>

<style></style>

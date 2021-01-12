<template>
  <div class="relative" :class="small ? null : 'shadow-xl'">
    <form
      class="w-full rounded-full"
      @submit.prevent
      :class="small ? 'bg-gray-100' : 'bg-white'"
    >
      <div class="flex items-center py-2">
        <input
          v-model="searchQuery"
          class="w-full ml-4 py-1 leading-tight placeholder-gray-400 transition duration-200 ease-out bg-transparent appearance-none focus:outline-none text-gray-700"
          type="text"
          placeholder="Rechercher"
          aria-label="Search"
        />
        <button
          class="text-gray-400 mr-4 transition duration-100 ease-out hover:text-gray-700 focus:outline-none"
          type="button"
          aria-label="Clear search field"
          @click="searchQuery = ''"
          v-show="searchQuery !== ''"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            class="w-4 h-4"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>
    </form>
    <transition
      enter-active-class="transition duration-100 ease-out"
      enter-class="transform scale-95 opacity-0"
      enter-to-class="transform scale-100 opacity-100"
      leave-active-class="transition duration-75 ease-in"
      leave-class="transform scale-100 opacity-100"
      leave-to-class="transform scale-95 opacity-0"
    >
      <div
        class="absolute z-10 mt-2 rounded-md shadow-lg left-0 right-0"
        v-if="elements.length"
      >
        <div class="bg-gray-50 rounded-md shadow-xs">
          <div
            class="py-1 divide-y-2 divide-gray-200"
            role="menu"
            aria-orientation="vertical"
            aria-labelledby="options-menu"
          >
            <component
              v-for="(element, index) of elements"
              :key="index"
              :to="element.path === '' ? null : element.path"
              :is="element.path === '' ? 'div' : 'nuxt-link'"
              class="block px-4 py-2 text-sm leading-5 text-gray-700 truncate transition duration-150 ease-out focus:outline-none"
              :class="
                element.path === ''
                  ? null
                  : 'hover:bg-gray-200 hover:text-gray-900'
              "
              role="menuitem"
            >
              <div
                class="text-gray-800 font-semibold"
                :class="small ? 'text-lg' : 'text-xl'"
              >
                {{ element.title }}
              </div>
              <div
                class=" whitespace-normal text-justify"
                :class="small ? null : 'text-lg'"
              >
                {{ element.description }}
              </div>
            </component>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  props: {
    small: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      searchQuery: "",
      elements: []
    };
  },
  watch: {
    async searchQuery(searchQuery) {
      if (!searchQuery) {
        this.elements = [];
        return;
      }
      this.elements = await this.$content()
        .only(["title", "path", "description"])
        .sortBy("createdAt", "asc")
        .limit(6)
        .search(searchQuery)
        .fetch();
      if (this.elements.length === 0) {
        this.elements.push({
          title: "Aucun résultat",
          path: "",
          description: "Essayez autre chose"
        });
      }
    },
    $route(to, from) {
      this.elements = [];
      this.searchQuery = "";
    }
  }
};
</script>

<style></style>

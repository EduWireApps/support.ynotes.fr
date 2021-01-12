<template>
  <div>
    <div
      class="flex items-center justify-center bg-center bg-cover h-72 relative"
      :style="
        'background-image: url(' + require('~/assets/images/hero.png') + ')'
      "
    >
      <div class="absolute inset-0 z-10">
        <div class="absolute inset-0 bg-black opacity-60"></div>
      </div>
      <div class="z-10 w-224 max-w-full px-4">
        <h1
          class="mb-4 text-3xl font-bold text-center text-white sm:text-4xl lg:text-6xl md:mb-8 xyz-nested "
        >
          Centre d'aide
        </h1>
        <SearchBar />
      </div>
    </div>
    <Container class="py-12">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione pariatur
      enim voluptate ab officiis fuga dolores voluptatum cum sapiente eos
      architecto sequi accusantium consequatur labore dolorum, vel vero eveniet
      sint quos, consequuntur delectus nobis eum quaerat odit. Iure earum in
      eaque nobis quidem, facilis architecto voluptatibus quam consectetur
      corporis voluptate, iusto dignissimos aut maiores fugiat ratione
      aspernatur cupiditate itaque eveniet delectus! Natus assumenda, sit
      voluptate ad, adipisci officia facere nisi maiores tenetur explicabo dolor
      autem nesciunt. Corrupti sunt architecto cum possimus ducimus. Ea
      voluptatem fuga odio esse cupiditate voluptas doloremque soluta provident
      at aperiam! Sequi, vero quibusdam modi nisi explicabo nesciunt a libero
      maxime. Deleniti, nostrum necessitatibus. Nisi veritatis sit dolorum,
      earum saepe officiis inventore sunt modi corrupti? Magni quam provident
      culpa repellat eveniet natus quia fuga, impedit blanditiis velit! Iste
      asperiores quam iusto blanditiis, ad doloribus architecto aperiam, vero,
      libero quos placeat voluptatem. Quasi nostrum molestias voluptas provident
      quod nihil. Repellendus numquam dolore reiciendis at dolores nihil
      voluptate illo facilis praesentium id nisi adipisci, incidunt hic sint
      facere inventore voluptates neque dolorum asperiores nobis tempore
      debitis. Distinctio ipsa cumque quo ut, blanditiis, aliquam est sed
      doloribus nemo error, natus fuga accusantium amet ratione tempora sapiente
      hic sunt saepe. Fugiat?
    </Container>
  </div>
</template>

<script>
export default {};
</script>

<style></style>

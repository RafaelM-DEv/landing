<template>
  <div class="flex justify-center bg-gray-500 h-[536px]">
    <div class="container flex justify-between relative">
      <div class="flex flex-col justify-center absolute px-8 py-4 h-full w-full items-center sm:items-start z-[1] text-black">
        <h1 class="text-3xl font-bold text-center sm:text-right">
          Lorem, ipsum dolor.amet consectetur
        </h1>
        <h3>Lorem ipsum dolor sit, amet consectetur</h3>
        <button class="bg-yellow-200 px-3 py-2 rounded-md w-[172px] mt-16 text-black">
          clique aqui
        </button>
      </div>
      <div class="flex justify-end absolute h-full w-full opacity-50">
        <img src="https://picsum.photos/882/530">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  setup () {}
}
</script>

<style lang="scss">
// opcional fullscreen section
.hero {
  .home {
    height: calc(100vh - 50px);
  }
}
</style>

<script setup>
  const route = useRoute()
  useHead({
    title: `${route.params.make ? userCarNameFormat(route.params.make) : 'Cars'} in ${userCarNameFormat(route.params.city)}`
  })
  definePageMeta({
    layout: 'custom'
  })
</script>

<template>
  <div>
    <div class="mt-32 flex">
    <NuxtErrorBoundary>
      <CarSideBar />
      <NuxtPage />
      <template #error="{ error }">
        <div class="flex flex-col justify-center items-center w-full mt-10">
          <h1 class="text-2xl">Ooops you found it</h1>
          <code> {{ error }}</code>
          <p>{{ error.message }}</p>
          <NuxtImg class="w-[600px] pt-10" src="https://w7.pngwing.com/pngs/677/284/png-transparent-tyrannosaurus-google-chrome-t-rex-runner-dinosaur-dinosaur-game-angle-white.png" alt="T rex"/>
          <button class="text-xl text-blue-500 underline" to="/" @click="error.value = null">Go back</button>
        </div>
      </template>
    </NuxtErrorBoundary>
    </div>
  </div>
</template>

<style scoped>

</style>
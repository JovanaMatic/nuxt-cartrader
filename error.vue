<script setup>
  const error = useError()
</script>

<template>
  <div class="flex flex-col justify-center items-center w-full mt-10">
    <h1 class="text-2xl">Ooops you found it</h1>
    <p>Status {{ error.statusCode }}</p>
    <p>{{ error.message }}</p>
    <NuxtImg class="w-[600px] pt-10" src="https://w7.pngwing.com/pngs/677/284/png-transparent-tyrannosaurus-google-chrome-t-rex-runner-dinosaur-dinosaur-game-angle-white.png" alt="T rex"/>
    <NuxtLink class="text-xl text-blue-500 underline" to="/">Go back</NuxtLink>
  </div>
</template>

<style scoped>

</style>
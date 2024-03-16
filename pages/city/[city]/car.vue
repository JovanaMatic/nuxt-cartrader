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
    <CarSideBar />
    <NuxtPage />
    </div>
  </div>
</template>

<style scoped>

</style>
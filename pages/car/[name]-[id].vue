<script setup>
  const route = useRoute()
  useHead({
    title: userCarNameFormat(route.params.name)
  })

  definePageMeta({
    layout: 'custom'
  })
</script>

<template>
  <div>
    <DetailHero />
    <DetailAttributes />
    <DetailDescription />
    <DetailReferral />
  </div>
</template>

<style scoped>

</style>
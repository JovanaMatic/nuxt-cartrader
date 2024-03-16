<script setup>
  const route = useRoute()
  useHead({
    title: userCarNameFormat(route.params.name)
  })
  definePageMeta({
    layout: 'custom'
  })
  const carId = route.params.id
  const { cars } = useCars()

  const filteredCar = computed(() => {
    return cars.find(car => car.id === Number(carId))
  })
</script>

<template>
  <div v-if="cars">
    <DetailHero :car="filteredCar" />
    <DetailAttributes :car="filteredCar"/>
    <DetailDescription :car="filteredCar"/>
    <DetailReferral />
  </div>
</template>

<style scoped>

</style>
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

  if(!filteredCar.value) {
    throw createError({
      statusCode: 404,
      message: `Car with ID ${route.params.id} does not exist`
    })
  }
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
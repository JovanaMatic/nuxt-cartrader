<script setup>
   const { cars } = useCars()
</script>

<template>
  <div>
    <div class="w-full">
      <CarCard v-for="car in cars" :key="car.id" :car="car" />
    </div>
  </div>
</template>

<style scoped>

</style>
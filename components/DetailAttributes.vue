<script setup>
  const props = defineProps({
    car: {
      type: Object,
      required: true
    }
  })
</script>

<template>
  <div>
    <div class="mr-10 mt-5 border-b pb-5">
      <div class="mt-2 flex text-lg">
        <p class="rounded text-lime-800 mr-3">✔</p>
        <p v-for="feature in car.features" :key="feature">{{ feature }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
  p {
    padding: 5px
  }
</style>
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
    <div class="mt-5">
      <p class="mb-10">{{ car.description }}
      </p>
    </div>
  </div>
</template>

<script setup>

</script>

<style scoped>

</style>
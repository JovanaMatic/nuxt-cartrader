<script setup>
import heartFilled from '~/assets/heartFilled.png'
import heartOutline from '~/assets/heartOutline.png'
  const props = defineProps({
    car: {
      type: Object,
      required: true
    },
    favored: {
      type: Boolean,
      required: true
    }
  })

  const emit = defineEmits(['favor'])

</script>

<template>
  <div>
    <div class="relative shadow border w-full overflow-hidden mb-5 cursor-pointer h-[200px]"
    >
    <img class="absolute w-7 top-2 z-20 right-5" :src="favored ? heartFilled : heartOutline" alt="heart" @click="emit('favor', car.id)"/>
      <div class="flex h-full" @click="navigateTo(`/car/${car.name}-${car.id}`)">
        <NuxtImg :src="car.url" class="w-[300px] h-full" alt="car image" />
          <div class="p-4 flex flex-col">
            <div>
              <h1 class="text-2xl text-blue-700">{{ car.name }}</h1>
              <p class="text-gray-700">{{ car.description }}.</p>
            </div>
              <h1 class="mt-auto text-xl">${{ car.price }}</h1>
          </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
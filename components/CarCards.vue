<script setup>
   const { cars } = useCars()

   const favorite = useLocalStorage('favorite', {})

   const handleFavored = (id) => {
    if (id in favorite.value) {
      delete favorite.value[id]
    } else {
      favorite.value = {
        ...favorite.value,
        [id]: true
      }
    }
   }
</script>

<template>
  <div>
    <div class="w-full">
      <ClientOnly>
        <CarCard v-for="car in cars" :key="car.id" :car="car" :favored="car.id in favorite" @favor="handleFavored" />
      </ClientOnly>
    </div>
  </div>
</template>

<style scoped>

</style>
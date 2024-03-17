<script setup>
  const modal = ref({
    make: false,
    location: false,
    price: false
  })

  const route = useRoute()
  const city = ref('')

  const updateModal = (modalValue) => {
    modal.value[modalValue] = !modal.value[modalValue]
  }

  const changeCity = () => {
    if (!city.value) return
    updateModal('location')
    navigateTo(`/city/${city.value}/car/${route.params.make}`)
    city.value = ''
  }
</script>

<template>
  <div>
    <div class="shadow border w-64 mr-10 z-30 h-[190px]">
        <div class="p-5 flex justify-between relative cursor-pointer border-b">
          <h3 @click="updateModal('location')">Location</h3>
          <h3 class="text-blue-400 capitalize">{{ route.params.city }}</h3>
          <div v-if="modal.location || modal.price" class="absolute border shadow left-72 p-5 top-1 bg-white -m-1">
            <input type="text" class="border p-1 rounded" v-model="city"/>
            <button @click="changeCity" class="bg-blue-400 w-full mt-2 rounded text-white p-1">Apply</button>
          </div>
        </div>
        <div class="p-5 flex justify-between relative cursor-pointer border-b">
          <h3 @click="updateModal('make')">Make</h3>
        <h3 class="text-blue-400 capitalize">Audi</h3>
        </div>
        <div class="p-5 flex justify-between relative cursor-pointer border-b">
          <h3 @click="updateModal('price')">Price</h3>
          <h3 class="text-blue-400 capitalize">50 000</h3>
        </div>
      </div>
  </div>
</template>

<style scoped>

</style>
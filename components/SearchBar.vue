<script setup>
  const city = ref('')
  const emptySearch = ref(false)
  const handleSearch = () => {
    if (!city.value) {
      emptySearch.value = true
      return
    }
    navigateTo(`/city/${city.value}/car`)
  }
</script>

<template>
  <div>
    <div :class="emptySearch ? 'border-red-400 border': ''" class="font-serif w-[1000px] text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto">
      <input type="text" class="py-3 w-full px-5 text-2xl rounded-full focus:outline-none" :placeholder="emptySearch ? 'Please enter city' : 'Search by city...'" v-model="city"/>
      <button @click="handleSearch" class="bg-sky-500 px-10 text-white">Search</button>
    </div>
  </div>
</template>

<style scoped>

</style>
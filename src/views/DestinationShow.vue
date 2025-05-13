<script setup>
import {useRoute} from 'vue-router'
import {computed} from "vue";
import sourceData from '@/data.json'

const route = useRoute()
const destinationId = computed(()=> {
  return parseInt(route.params.id)
})

const destination = computed(() => {
  return sourceData.destinations.find(
      (destination) => destination.id === destinationId.value)
})
</script>

<template>
  <h2>{{destination.name}}</h2>
  <section class="destination-details">
    <img :src="`/images/${destination.image}`" :alt="destination.name">
    <p>{{ destination.description }}</p>
  </section>
</template>

<style scoped>

</style>
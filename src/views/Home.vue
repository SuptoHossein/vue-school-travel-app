<script setup>
import sourceData from '@/data.json'
</script>

<template>
  <div class="home">
    <h1>All Destinations</h1>
    <div class="destinations">
      <router-link
          v-for="destination in sourceData.destinations"
          :key="destination.id"
          :to="{name: 'destination.show', params: {id: destination.id, slug: destination.slug}}">
        <h2>{{destination.name}}</h2>
        <img :src="`/images/${destination.image}`" :alt="destination.name">
      </router-link>
    </div>
  </div>
</template>

<style scoped>

</style>
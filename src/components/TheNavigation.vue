<script setup>
import sourceData from '@/data.json'
</script>

<template>
  <div id="nav">
    <router-link id="logo" to="/">Vue School Travel App</router-link>

    <router-link
        v-for="destination in sourceData.destinations"
        :key="destination.id"
        :to="{name: 'destination.show', params: {id: destination.id, slug: destination.slug}}">{{ destination.name }}</router-link>
  </div>
</template>

<style scoped>

</style>
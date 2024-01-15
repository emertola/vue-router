<script setup lang="ts">
import { useRoute } from 'vue-router'
import cars from '@/data/cars.json'

const route = useRoute()
const car = cars.find((car) => car.id === +route.params.id)
</script>

<template>
  <div>
    <h1>Contact Info</h1>
    <p>{{ car?.contact.dealer }}</p>
    <p>{{ car?.contact.phone }}</p>
  </div>
</template>

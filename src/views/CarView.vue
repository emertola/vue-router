<script setup lang="ts">
import { RouterView, useRoute, useRouter } from 'vue-router'
import cars from '@/data/cars.json'

const route = useRoute()
const router = useRouter()
const { params } = route
const selectedCar = cars.find((car) => car.id === +params.id)

const viewContact = (path: string): void => {
  router.push(path)
}
</script>

<template>
  <div>
    <h1>Car View</h1>
    <p>{{ selectedCar?.name }}</p>
    <p>{{ selectedCar?.year }}</p>
    <p>{{ selectedCar?.price || 0 }}</p>

    <!-- <RouterLink to="./contact">
      <button type="button">View Contact</button>
    </RouterLink> -->
    <button type="button" @click="viewContact(`./${selectedCar?.id}/contact`)">View Contact</button>

    <RouterView />
  </div>
</template>

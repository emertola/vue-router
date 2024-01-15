<script setup lang="ts">
import { RouterLink } from 'vue-router'
import cars from '@/data/cars.json'
</script>

<template>
  <main>
    <div>
      <h1>Home</h1>
      <div class="cars">
        <RouterLink :to="`/cars/${car.id}`" v-for="car in cars" :key="car.id" href="">
          {{ car.name }}
        </RouterLink>
      </div>
    </div>
  </main>
</template>

<style scoped>
.cars {
  display: flex;
}

.cars a {
  text-decoration: none;
  width: 100%;
  box-shadow: 1px 1px 1px gray;
  margin: 10px;
}
</style>

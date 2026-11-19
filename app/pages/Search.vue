<template>
    <h1>Pàgina de cerca</h1>

    <div class="llista-receptes">
        <ItemCard v-for="recepta in items" :key="recepta.idMeal" :item="recepta" />
    </div>

</template>

<script setup>
import { createCommunicationManager } from '~/services/communicationManager'

const communication = createCommunicationManager()
const items = ref([])
items.value = await communication.searchItems('chicken')

</script>

<style scoped>
h1 {
  font-size: 2.2rem;
  font-weight: 800;
  color: #1a202c;
  margin: 0 0 28px 0;
  letter-spacing: -0.5px;
  position: relative;
  display: inline-block;
}

h1::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -6px;
  width: 50px;
  height: 4px;
  background: #00aeef;
  border-radius: 99px;
}

.llista-receptes {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 24px;
}
</style>
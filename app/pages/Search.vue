<template>
    <h1>Pàgina de cerca</h1>

    <div class="llista-receptes">
        <ItemCard v-for="recepta in items" :key="recepta.idMeal" :item="recepta" />
    </div>

</template>

<script setup>

const communication = createCommunicationManager()
const items = ref([])
items.value = await communication.searchItems('chicken')

</script>

<style scoped></style>
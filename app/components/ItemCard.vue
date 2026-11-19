<template>
  <div class="card">
    <!-- Funciona tant per a receptes com per a categories -->
    <img
      :src="item.strMealThumb || item.strCategoryThumb"
      :alt="item.strMeal || item.strCategory"
      class="card-img"
    />
    <div class="info">
      <h3>{{ item.strMeal || item.strCategory }}</h3>
      <p v-if="item.strCategory && item.strMeal" class="badge">
        {{ item.strCategory }}
      </p>
      <p v-if="item.strCategoryDescription" class="desc">
        {{ item.strCategoryDescription.slice(0, 100) }}...
      </p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  item: {
    type: Object,
    required: true
  }
})
</script>

<style scoped>
.card {
  border: 1px solid #e0e0e0;
  border-radius: 10px;
  overflow: hidden;
  background: #ffffff;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.06);
  display: flex;
  flex-direction: column;
  transition: transform 0.2s ease;
}

.card:hover {
  transform: translateY(-4px);
}

.card-img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  background: #f0f0f0;
}

.info {
  padding: 12px;
  display: flex;
  flex-direction: column;
  gap: 6px;
}

h3 {
  margin: 0;
  font-size: 1.05rem;
  color: #231f20;
}

.badge {
  margin: 0;
  color: #00aeef;
  font-weight: 600;
  font-size: 0.85rem;
}

.desc {
  margin: 0;
  font-size: 0.85rem;
  color: #666;
}
</style>

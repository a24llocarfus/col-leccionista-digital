<template>
  <div class="card">
    <img :src="item.strMealThumb" :alt="item.strMeal" />
    <div class="info">
      <h3>{{ item.strMeal }}</h3>
      <p v-if="item.strCategory">{{ item.strCategory }}</p>
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
  background: #ffffff;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  display: flex;
  flex-direction: column;
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
  border: 1px solid #edf2f7;
  cursor: pointer;
}

.card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 28px rgba(0, 174, 239, 0.18);
  border-color: #00aeef;
}

.card img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  display: block;
  transition: transform 0.4s ease;
}

.card:hover img {
  transform: scale(1.05);
}

.info {
  padding: 18px;
  display: flex;
  flex-direction: column;
  gap: 8px;
  flex: 1;
}

.info h3 {
  margin: 0;
  font-size: 1.15rem;
  font-weight: 700;
  color: #1a202c;
  line-height: 1.35;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  transition: color 0.2s ease;
}

.card:hover .info h3 {
  color: #00aeef;
}

.info p {
  margin: 0;
  font-size: 0.8rem;
  font-weight: 700;
  color: #00aeef;
  background: #e6f7fd;
  align-self: flex-start;
  padding: 4px 10px;
  border-radius: 20px;
  letter-spacing: 0.5px;
  text-transform: uppercase;
}
</style>
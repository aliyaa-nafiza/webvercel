<template>
  <div class="team-card">
    <div class="avatar">
      {{ inisial }}
    </div>
    <h3 class="nama">{{ nama }}</h3>
    <p class="jabatan">{{ jabatan }}</p>
  </div>
</template>

<script setup>
const props = defineProps(['nama', 'jabatan'])

// Mengambil inisial dari nama (huruf pertama tiap kata)
const inisial = props.nama
  .split(' ')
  .map(kata => kata[0])
  .join('')
  .toUpperCase()
</script>

<style scoped>
.team-card {
  background: #ffffff;
  border-radius: 12px;
  padding: 24px;
  text-align: center;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease;
}

.team-card:hover {
  transform: translateY(-4px);
}

.avatar {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: #f6ca3b;
  color: #ffffff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: bold;
  margin: 0 auto 16px;
}

.nama {
  margin: 0 0 4px;
  font-size: 1.1rem;
  color: #1f2937;
}

.jabatan {
  margin: 0;
  font-size: 0.9rem;
  color: #6b7280;
}
</style>
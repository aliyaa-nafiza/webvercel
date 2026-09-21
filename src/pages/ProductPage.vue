<script setup>
import ProductCard from '../components/ProductCard.vue'
 
const daftarProduk = [
  { id: 1, nama: 'Fresh Flowers', harga: 25000, gambar: 
'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQrhiFgSMrOJeTtOlnlOaXrNXGgjWlXawkLrGXdYA2R5Q&s=10' },
  { id: 2, nama: 'Bucket Bunga', harga: 35000, gambar: 
'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR9ZN2TKirD50Mw0eS-qMn4V5Ihl6yjjYUQdCSmwi0mFg&s=10' },
  { id: 3, nama: 'Pupuk', harga: 23000, gambar: 
'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSVJuqCkHfSg9oked0qJeNjXAL9hP6zYFensvqmgkNrOQ&s=10' },
]
</script>
 
<template>``
  <main>
    <h1>Produk Kami</h1>
    <div class="grid">
      <ProductCard
        v-for="produk in daftarProduk"
        :key="produk.id"
        :nama="produk.nama"
        :harga="produk.harga"
        :gambar="produk.gambar"
      />
    </div>
  </main>
</template>
 
<style scoped>
.grid {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}
</style>
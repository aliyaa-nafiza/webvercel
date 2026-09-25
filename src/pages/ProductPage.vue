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

<template>
  <main class="min-h-screen bg-[#F2F5EE] px-6 py-14">
    <div class="mx-auto max-w-6xl">
      <h1 class="mb-10 font-['Fraunces',serif] text-3xl text-[#1F2E23] sm:text-4xl">
        Produk Kami
      </h1>

      <div class="produk-grid grid grid-cols-2 gap-5 sm:grid-cols-3 lg:grid-cols-4">
        <ProductCard
          v-for="produk in daftarProduk"
          :key="produk.id"
          :nama="produk.nama"
          :harga="produk.harga"
          :gambar="produk.gambar"
        />
      </div>
    </div>
  </main>
</template>

<style>
/* Kalau font Fraunces sudah di-import di App.vue / index.html, baris ini boleh dihapus */
@import url("https://fonts.googleapis.com/css2?family=Fraunces:wght@400;500;600&display=swap");

/*
  FALLBACK: memaksa card sejajar (grid) walau Tailwind belum/gagal ke-compile
  di project kamu. Kalau Tailwind sudah kebukti jalan normal, blok ini
  boleh dihapus karena class Tailwind di atas sudah cukup.
*/
.produk-grid {
  display: grid !important;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1.25rem;
}
@media (min-width: 640px) {
  .produk-grid {
    grid-template-columns: repeat(3, minmax(0, 1fr));
  }
}
@media (min-width: 1024px) {
  .produk-grid {
    grid-template-columns: repeat(4, minmax(0, 1fr));
  }
}
</style>
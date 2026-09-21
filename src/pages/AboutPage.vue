<template>
  <div class="about-page">

    <!-- Bagian 1: Cerita Kami -->
    <section class="cerita-kami">
      <h1>Cerita Kami</h1>
      <div class="cerita-content">
        <div class="cerita-teks">
          <p>
            Di BUNGA ABADI, kami percaya bahwa bunga bukan sekadar tanaman, 
            melainkan sebuah pesan tanpa kata yang mampu menyampaikan rasa cinta, bahagia, hingga simpati terdalam.
          </p>
          <p>
            Perjalanan kami dimulai dari kecintaan pada keindahan alam dan keinginan untuk membantu
             Anda merayakan setiap momen berharga. Kami berkomitmen untuk menyediakan bunga segar dengan kualitas terbaik,
              yang dipilih dan dirangkai langsung oleh tangan-tangan kreatif floris kami.
               Setiap lembar kelopak dan helai daun kami tata dengan penuh perhatian untuk memastikan pesan tulus Anda tersampaikan dengan sempurna kepada orang tersayang.
          </p>
          <p>
            Visi kami sederhana: Menjadi toko bunga terpercaya yang menjembatani kebahagiaan dan kehangatan hubungan antarmanusia melalui keindahan setiap rangkaian bunga.
          </p>
        </div>
        <div class="cerita-gambar">
          <!-- Ganti src dengan gambar asli jika tersedia -->
          <div class="placeholder-img">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRuPXAgtnAvzDi0vWlyKYOcvbnq793QiLnAaWeAiwxWJQ&s=10" alt="">
          </div>
        </div>
      </div>
    </section>

    <!-- Bagian 2: Tim Kami -->
    <section class="tim-kami">
      <h1>Tim Kami</h1>
      <div class="tim-grid">
        <TeamCard
          v-for="anggota in daftarTim"
          :key="anggota.id"
          :nama="anggota.nama"
          :jabatan="anggota.jabatan"
        />
      </div>
    </section>

  </div>
</template>

<script setup>
import TeamCard from '../components/TeamCard.vue'

const daftarTim = [
  { id: 1, nama: 'Leyaa', jabatan: 'Founder & CEO' },
  { id: 2, nama: 'Marchel', jabatan: 'UI/UX Designer' },
  { id: 3, nama: 'Angel', jabatan: 'Backend Developer' },
  { id: 4, nama: 'Didin', jabatan: 'Marketing Manager' }
]
</script>

<style scoped>
img {
height: 380px;
width: 480px;
border-radius: 15px;

}

.about-page {
  max-width: 1000px;
  margin: 0 auto;
  padding: 40px 20px;
}

/* === Cerita Kami === */
.cerita-kami h1 {
  margin-bottom: 24px;
  color: white;
}

.cerita-content {
  display: flex;
  align-items: center;
  gap: 40px;
}

.cerita-teks {
  flex: 1;
}

.cerita-teks p {
  line-height: 1.7;
  color:white;
  margin-bottom: 12px;
}

.cerita-gambar {
  flex: 1;
}

.placeholder-img {
  width: 100%;
  height: 280px;
  background: #f3f4f6;
  border-radius: 12px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: 3rem;
  color: #9ca3af;
}

.placeholder-img span {
  font-size: 0.9rem;
  margin-top: 8px;
}

/* === Tim Kami === */
.tim-kami {
  margin-top: 60px;
}

.tim-kami h1 {
  margin-bottom: 24px;
  color: white;
}

.tim-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 24px;
}
</style>
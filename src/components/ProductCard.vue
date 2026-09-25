<script setup>
import { ref } from 'vue'

defineProps(['nama', 'harga', 'gambar'])

const gambarDipilih = ref(null)

function bukaPreview(src) {
  gambarDipilih.value = src
}

function tutupPreview() {
  gambarDipilih.value = null
}
</script>

<template>
  <div
    class="kartu group w-full max-w-[220px] overflow-hidden rounded-2xl border border-[#E4E8DE] bg-white shadow-sm transition-shadow duration-300 hover:shadow-lg"
  >
    <div class="kartu__gambar-wrap aspect-square overflow-hidden bg-[#F2F5EE]">
      <img
        :src="gambar"
        :alt="nama"
        @click="bukaPreview(gambar)"
        class="kartu__gambar h-full w-full cursor-zoom-in object-cover transition-transform duration-500 ease-out group-hover:scale-110"
      />
    </div>
    <div class="kartu__body p-4 text-left">
      <h3 class="font-['Fraunces',serif] text-base font-medium leading-snug text-[#1F2E23]">
        {{ nama }}
      </h3>
      <p
        class="mt-2 inline-block rounded-full bg-[#F4E4E1] px-2.5 py-0.5 text-sm font-medium text-[#B15E63]"
      >
        Rp {{ harga.toLocaleString('id-ID') }}
      </p>
    </div>
  </div>

  <Transition name="fade">
    <div
      v-if="gambarDipilih"
      @click="tutupPreview"
      class="preview-overlay fixed inset-0 z-50 flex cursor-zoom-out items-center justify-center bg-black/80 p-6 backdrop-blur-sm"
    >
      <img
        :src="gambarDipilih"
        class="preview-gambar max-h-[85vh] max-w-[90vw] rounded-2xl shadow-2xl"
        @click.stop
      />
    </div>
  </Transition>
</template>

<style scoped>
/* Transisi buka/tutup preview — dipakai otomatis oleh <Transition name="fade"> */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/*
  FALLBACK CSS BIASA — jaga-jaga kalau Tailwind belum/gagal ke-compile
  di project kamu. Kalau Tailwind sudah kebukti jalan normal, blok ini
  aman dihapus karena class Tailwind di atas sudah cukup sendirian.
*/
.kartu {
  display: block !important;
  width: 100% !important;
  max-width: 220px !important;
  border-radius: 16px !important;
  border: 1px solid #e4e8de !important;
  background: #8b558b !important;
  overflow: hidden !important;
  box-sizing: border-box !important;
}
.kartu__gambar-wrap {
  width: 100% !important;
  aspect-ratio: 1 / 1 !important;
  overflow: hidden !important;
  background: #f2f5ee !important;
}
.kartu__gambar {
  width: 100% !important;
  height: 100% !important;
  object-fit: cover !important;
  display: block !important;
}
.kartu__body {
  padding: 16px !important;
  text-align: left !important;
}
.preview-overlay {
  position: fixed !important;
  inset: 0 !important;
  z-index: 50 !important;
  display: flex !important;
  align-items: center !important;
  justify-content: center !important;
  background: rgba(0, 0, 0, 0.8) !important;
  padding: 24px !important;
}
.preview-gambar {
  max-width: 90vw !important;
  max-height: 85vh !important;
  border-radius: 16px !important;
}
</style>
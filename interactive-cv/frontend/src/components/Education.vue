<script setup>
import SectionTitle from './SectionTitle.vue';

// Data ini akan kita pindah ke backend nanti
// Consider moving this data to a Pinia store or a separate data file
// if it grows, even before backend integration.
const educationHistory = [
  { id: 1, period: '2022 - Sekarang', institution: 'Universitas Gadjah Mada', major: 'S1 - Teknik Informatika' },
  { id: 2, period: '2019 - 2022', institution: 'SMA Negeri 1 Teladan Yogyakarta', major: 'MIPA' }
];
</script>

<template>
  <section id="pendidikan" class="py-20 bg-white">
    <div class="container mx-auto px-6">
      <SectionTitle title="Riwayat Pendidikan" />

      <div class="relative">
        <div class="absolute h-full border-r-2 border-gray-300 left-1/2 -translate-x-1/2"></div>

        <div
          v-for="(edu, index) in educationHistory"
          :key="edu.id"
          class="mb-8 flex items-center w-full"
          :class="{ 'justify-between': index % 2 === 0, 'flex-row-reverse': index % 2 !== 0 }"
        >
          <div
            class="w-1/2"
            :class="{ 'pr-8 text-right': index % 2 === 0, 'pl-8 text-left': index % 2 !== 0 }"
          >
            <p class="font-semibold text-blue-600">{{ edu.period }}</p>
            <h3 class="text-2xl font-bold text-gray-800">{{ edu.institution }}</h3>
            <p class="text-gray-600">{{ edu.major }}</p>
          </div>

          <div class="w-1/2 flex" :class="{ 'justify-start': index % 2 === 0, 'justify-end': index % 2 !== 0 }">
            <div class="w-4 h-4 bg-blue-600 rounded-full z-10"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

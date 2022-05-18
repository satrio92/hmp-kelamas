<template>
  <div class="home font-poppins pb-10">
    <Hero />
    <div class="px-20 flex flex-col gap-4">
      <div>
        <button class="bg-green-500 px-6 py-3 rounded-md font-semibold text-white flex gap-2"><i class="bi bi-plus-circle"></i> Tambah Buku</button>
      </div>
      <div class="w-full border-t-2 border-b-2 border-green-500 py-2 flex justify-between">
        <p class="font-semibold">{{ startData }} - {{ endData }} / halaman {{ currentPage }} dari {{ totalPage }}</p>
        <div class="flex gap-4 text-2xl">
          <i class="bi" :class="prevBtn ? 'bi-arrow-left-square-fill text-green-500 cursor-pointer' : 'bi-arrow-left-square text-gray-300 cursor-default'" @click="prevPage"></i>
          <i class="bi" :class="nextBtn ? 'bi-arrow-right-square-fill text-green-500 cursor-pointer' : 'bi-arrow-right-square text-gray-300 cursor-default'" @click="nextPage"></i>
        </div>
      </div>
      <table class="w-full">
        <tr class="bg-green-500 text-white mb-2">
          <th class="border-[1px] py-2 px-4 font-semibold">Timestamp</th>
          <th class="border-[1px] py-2 px-4 font-semibold">Kategori Buku</th>
          <th class="border-[1px] py-2 px-4 font-semibold w-1/6">Judul Buku</th>
          <th class="border-[1px] py-2 px-4 font-semibold">Nama Pengarang</th>
          <th class="border-[1px] py-2 px-4 font-semibold">Tahun terbit</th>
          <th class="border-[1px] py-2 px-4 font-semibold">Ebbok</th>
        </tr>
        <tr>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">24/01/2022 18:28:32</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">Biologi</td>
          <td class="border-[1px] border-green-500 py-2 px-4">BIOLOGI Edisi Kedelapan Jilid 1</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">Campbell</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">2010</td>
          <td class="border-[1px] border-green-500 py-2 px-4">https://drive.google.com/drive/u/1/folders/1XP_s4ivglO_CSLubHrZnC2CAIm5oNHOZ</td>
        </tr>
        <tr>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">24/01/2022 18:28:32</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">Biologi</td>
          <td class="border-[1px] border-green-500 py-2 px-4">BIOLOGI Edisi Kedelapan Jilid 1</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">Campbell</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">2010</td>
          <td class="border-[1px] border-green-500 py-2 px-4">https://drive.google.com/drive/u/1/folders/1XP_s4ivglO_CSLubHrZnC2CAIm5oNHOZ</td>
        </tr>
        <tr>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">24/01/2022 18:28:32</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">Biologi</td>
          <td class="border-[1px] border-green-500 py-2 px-4">BIOLOGI Edisi Kedelapan Jilid 1</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">Campbell</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">2010</td>
          <td class="border-[1px] border-green-500 py-2 px-4">https://drive.google.com/drive/u/1/folders/1XP_s4ivglO_CSLubHrZnC2CAIm5oNHOZ</td>
        </tr>
        <tr>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">24/01/2022 18:28:32</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">Biologi</td>
          <td class="border-[1px] border-green-500 py-2 px-4">BIOLOGI Edisi Kedelapan Jilid 1</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">Campbell</td>
          <td class="border-[1px] border-green-500 py-2 px-4 text-center">2010</td>
          <td class="border-[1px] border-green-500 py-2 px-4">https://drive.google.com/drive/u/1/folders/1XP_s4ivglO_CSLubHrZnC2CAIm5oNHOZ</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>

import Hero from '@/components/Hero.vue';

export default {
  name: "Home",
  components: {
    Hero,
  },
  data() {
    return {
      currentPage: 1,
      dataPerPage: 15,
      totalPage: 3,
      nextBtn: true,
      prevBtn: false
    }
  },
  computed: {
    startData() {
      return ((this.currentPage - 1) * this.dataPerPage) + 1
    },
    endData() {
      return this.currentPage * this.dataPerPage
    }
  },
  methods: {
    nextPage() {
      if(this.currentPage != this.totalPage) {
        if(this.currentPage == (this.totalPage - 1)) {
          this.nextBtn = false
        }
        this.currentPage++
        this.prevBtn = true
      }
    },
    prevPage() {
      if(this.currentPage != 1) {
        if(this.currentPage == 2) {
          this.prevBtn = false
        }
        this.currentPage--
        this.nextBtn = true
      }
    }
  }
};
</script>

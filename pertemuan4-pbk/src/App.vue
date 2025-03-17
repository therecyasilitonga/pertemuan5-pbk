<script setup>
 import { ref } from 'vue'

 const namapanggilan = ref('Therecya Silitonga - 233510300')
 const textinterpolation = ref(' 4D')

 const selected = ref(' ')

 const tes1 = ref('tes1 ')
 const warna= ref('')

function aksi() {
  if (tes1.value === 'ini adalah tes1') {
    tes1.value = ' ini adalah tes1 yang sudah diubah'
    warna.value ='red'
  } else {
    tes1.value = 'ini adalah tes1'
    warna.value ='blue'
  }
  
}

const usia = ref (0)



</script>

<template>
  <h1> TUGAS PERTEMUAN 4 </h1>
  <h1>PEMROGRAMAN BERBASIS KOMPONEN</h1>
  <div>{{ namapanggilan }}</div>
  <p>{{ textinterpolation }}</p>
  <hr>
  <hr>



  <div>JURUSAN YANG DIPILIH: {{ selected }}</div>
  <select v-model="selected">
    <option disabled value="">JURUSAN</option>
    <option>TEKNIK INFORMATIKA</option>
    <option>BAHASA INGGRIS</option>
    <option>PSIKOLOGI</option>
    <option>PENJASKES</option>
  </select>

  <hr>
  <div :style = "{color : warna}"> {{ tes1 }}</div>
  <button @click = "aksi">Button</button>
  <hr>

  
  <input type="text" v-model.number="usia" placeholder="Masukkan usia Anda" />

<div>
  <p>Usia Anda : {{ usia }}</p>
  <p v-if="usia < 15">Anda masih anak-anak</p>
  <p v-else-if="usia >= 15 && usia < 60">Anda sudah dewasa</p>
  <p v-else-if="usia >= 60">Anda sudah lansia</p>
  <p v-else>Umur tidak valid, silakan masukkan usia yang benar</p>
</div>



</template>

<style scoped>
</style>

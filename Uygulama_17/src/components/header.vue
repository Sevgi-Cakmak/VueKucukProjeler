<!-- header.vue -->
<template>
    <!-- Başlık bileşeninin şablonu -->
    <header>
      <!-- Başlık bilgisini görüntüler ve tıklama olayı tetikler -->
      <h1 v-on:click="changeTitle">{{ title }}</h1>
    </header>
  </template>
  
  <script>
  export default {
    props: {
      // Başlık prop'unu tanımlar
      title: {
        type: String, // Dize tipinde bir değer olmalıdır
        required: true // Zorunlu bir prop'tur
      }
    },
    methods: {
      // Başlığı değiştiren yöntem
      changeTitle: function() {
        // 'basligiDegistir' olayını tetikler ve yeni başlık gönderir
        this.$emit("basligiDegistir", "Alt Bileşen Tarafindan Değiştirilen Başlik")
      }
    }
  }
  </script>
  
  <style scoped>
  /* Bileşene özgü stiller */
  header {
    background: lightgreen;
    padding: 10px;
  }
  h1 {
    color: #222;
    text-align: center;
  }
  </style>
  
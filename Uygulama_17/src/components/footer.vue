<!-- footer.vue -->
<template>
    <!-- Altbilgi bileşeninin şablonu -->
    <footer>
      <!-- Telif hakkı, yıl ve başlık bilgisini görüntüler -->
      <p>{{ copyright }} - {{ year }} - {{ title }}</p>
    </footer>
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
    data() {
      return {
        // Telif hakkı ve yıl veri alanlarını tanımlar
        copyright: "Tüm Haklari Saklidir. (c)",
        year: 2023
      }
    }
  }
  </script>
  
  <style scoped>
  /* Bileşene özgü stiller */
  footer {
    background: #222;
    padding: 6px;
  }
  p {
    color: lightgreen;
    text-align: center;
  }
  </style>
  

<!-- article.vue -->
<template>
    <!-- Kullanıcı listesi ve kullanıcı sil butonunu içeren bileşenin şablonu -->
    <div id="users">
      <ul>
        <!-- Kullanıcıları listeleyen döngü -->
        <li v-for="user in users" v-on:click="user.show = !user.show">
          <!-- Kullanıcı adını görüntüler -->
          <h2>{{ user.name }}</h2>
          <!-- Kullanıcı özelliklerini görüntüler -->
          <p v-show="user.show">{{ user.spec }}</p>
        </li>
      </ul>
      <!-- Kullanıcı sil butonu -->
      <button v-on:click="deleteUser">Kullanici Sil</button>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      // Kullanıcılar prop'unu tanımlar
      users: {
        type: Array, // Dizi tipinde bir değer olmalıdır
        required: true // Zorunlu bir prop'tur
      }
    },
    methods: {
      // Kullanıcıyı silen yöntem
      deleteUser: function() {
        this.users.pop(); // Kullanıcıları içeren diziden son kullanıcıyı kaldırır
      }
    }
  }
  </script>
  
  <style scoped>
  /* Bileşene özgü stiller */
  #users {
    width: 100%;
    max-width: 1200px;
    margin: 40px auto;
    padding: 0 20px;
    box-sizing: border-box;
  }
  ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
  }
  li {
    flex-grow: 1;
    flex-basis: 300px;
    text-align: center;
    padding: 30px;
    border: 1px solid #222;
    margin: 10px;
  }
  </style>
  

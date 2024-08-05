<!-- app.vue -->
<template>
  <!-- Ana bileşenin şablonu -->
  <!-- app-header, app-article ve app-footer bileşenlerini içerir -->
  <app-header v-bind:title="title" v-on:basligiDegistir="updateTitle($event)"></app-header>
  <app-article v-bind:users="users"></app-article>
  <app-footer v-bind:title="title"></app-footer>

</template>

<script>
import Header from './components/header.vue'
import Article from './components/article.vue'
import Footer from './components/footer.vue'


export default {
  components: {
    "app-header": Header, // Başlık bileşenini içeri aktarır
    "app-article": Article, // Makale bileşenini içeri aktarır
    "app-footer": Footer // Altbilgi bileşenini içeri aktarır
   
  },
  data() {
    return {
      // Başlık ve kullanıcılar veri alanlarını tanımlar
      title: "Webtangular", // Başlık verisini tanımlar
      users: [ // Kullanıcılar verisini tanımlar
        {name: "Gökhun", spec: "Geliştirici", show: false},
        {name: "Elif", spec: "Stratejist", show: false},
        {name: "Han", spec: "Daha bebek", show: false},
        {name: "Alper", spec: "Patron", show: false},
        {name: "Yağız", spec: "Patron yavrusu", show: false},
        {name: "Zahide", spec: "Ev hanımı", show: false},
      ]
    }
  },
  methods: {
    // Başlığı güncelleyen yöntem
    updateTitle: function(degisenBaslik) {
      this.title = degisenBaslik;
    }
  }
}
</script>



<template>
  <!-- Data dan Method -->
  <h2>Nama : {{ nama }}</h2>
  <button v-on:click="changeName">Change Name</button>

  <!-- Data Binding -->
  <br><br><a v-bind:href="url">MY INSTAGRAM</a>

  <!-- 2-Way Data Binding -->
  <br><br><input type="text" v-model="inputName">
  <br>{{ inputName }}

  <!-- Condisional dan Looping -->
  <div v-if="products.length">
    <ul>
      <li v-for="item in products" :key="item.id">
        {{ item.title }} - {{ item.price }}
      </li>
    </ul>
  </div>
  <div v-else>
    <p>Datas Not Found</p>
  </div>

</template>

<script>

export default {
  name: 'App',

  data() {
    return {
      nama: "Radyan Bintang H.",
      url: "https://instagram.com/radyanbintang",
      inputName: "",
      products: [
        { id: 1, title: "Aqua", price: 3000 },
        { id: 2, title: "Cleo", price: 2000 },
        { id: 3, title: "LeMineral", price: 4000 },
      ]
    }
  },
  methods: {
    changeName() {
      this.nama = "Naruto"
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

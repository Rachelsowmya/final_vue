<template>
  <div id="app">
    <MyHeader />
    <Listv :products="products" />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import Listv from './components/Listv.vue' 

export default {
  name: 'App',
  components: {
    MyHeader,
    Listv
  },
  data() {
    return {
      products: []
    }
  },
  methods: {
    async fetchproducts() {
      try {
        const res = await fetch('https://rachel-node.onrender.com/api');
        const data = await res.json();
        console.log(data);
        return data.products; 
      } catch (error) {
        console.error('Error fetching products:', error);
        return [];
      }
    },
    async loadProducts() {
      this.products = await this.fetchproducts();
    }
  },
  async created() {
    await this.loadProducts();
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
  max-width: 800px;
  margin: auto;
}
</style>

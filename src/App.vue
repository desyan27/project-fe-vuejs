<template>
  <div>
    <Navbar />
    <Banner />
    <div class="flex items-center justify-center py-4">
      <h1 class="text-zinc-950 font-semibold text-2xl">Featured Product</h1>
    </div>
    <div class="grid lg:grid-cols-3 lg:grid-rows-2 sm:grid-cols-2 sm:grid-rows-3 lg:gap-4 sm:gap-2">
      <div class="bg-white overflow-hidden mx-auto shadow-lg" v-for="product in products.slice(6, limit)" :key="product.id">
        <Product :product="product" />
      </div>
    </div>
    <div class="grid grid-cols-1 grid-rows-1 gap-0 mt-10 mb-11">
      <Banner1 />
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Banner from './components/Banner.vue';
import Product from './components/Product.vue';
import Banner1 from './components/Banner1.vue';
import Footer from './components/Footer.vue';
import axios from 'axios';

export default {
  name: "App",
  components: {
    Navbar,
    Banner,
    Product,
    Banner1,
    Footer,
  },
  data() {
    return {
      products: []
    }
  },
  methods: {
    setProduct(data) {
      this.products = data
    }
  },
  mounted() {
    const apiUrl = 'https://sistemtoko.com/public/demo/product';

    axios.get(apiUrl)
      .then((response) => this.setProduct(response.data.aaData))
      .catch((error) => console.log(error))
  },
};
</script>

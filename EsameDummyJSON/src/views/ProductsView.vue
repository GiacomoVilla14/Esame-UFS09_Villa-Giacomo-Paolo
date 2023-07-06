<script>

import Products from "@/components/Products.vue";

export default {
  name: "ProductsView",
  data() {
    return {
      products: []
    }
  },
  components: {
    Products
  },
  methods: {
    getProducts() {
      fetch('https://dummyjson.com/products/')
          .then(res => res.json())
          .then(json => this.products = json.products)
    },
  },
  created() {
    this.getProducts()
  }
}
</script>

<template>
  <Products v-for="product in this.products" :id="product.id" :titolo="product.title" :thumbn="product.thumbnail"
            :description="product.description" :key="product.id"></Products>
</template>

<style scoped>

</style>
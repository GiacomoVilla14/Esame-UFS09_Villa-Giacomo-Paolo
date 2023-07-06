<script>
import Cart from "@/components/Cart.vue";
import products from "@/components/Products.vue";

export default {
  name: "CartView",
  components: {
    Cart
  },
  setup() {
    return {
      products: []
    }
  },
  methods: {
    addToCart(product) {
      this.products.push(product)
    }
  },
  mounted() {
    console.log(products)
  }
}
</script>

<template @add-to-cart="addToCart">
  <Cart v-for="product in products" :key="product.id" :prodotto="product"></Cart>
</template>

<style scoped>

</style>
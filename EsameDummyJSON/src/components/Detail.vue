<script>
import {defineComponent} from 'vue'

export default {
  name: "Detail",
  data() {
    return {
      product: {}
    }
  },
  created() {
    const {id} = this.$route.params;
    fetch('https://dummyjson.com/products/' + id)
        .then(res => res.json())
        .then(json => this.product = json)
    alert(JSON.stringify(this.$route.params))
  },
  methods: {
    addToCart() {
      this.$emit("add-to-cart", this.product)
    }
  }
}
</script>

<template>
  <div class="container">
    <h1>{{ product.title }}</h1>
    <img :src="product.thumbnail" alt="`${{product.title}}`">
    <h3>
      {{ product.description }}
    </h3>
    <img v-for="immagine in product.images" :src="immagine" :key="immagine" alt="Immagine">
    <button @click="addToCart(product)">Aggiungi al carrello</button>
  </div>
</template>

<style scoped>
.container {
  border: solid 1px white;
  border-radius: 20px;
  padding: 20px;
}
</style>
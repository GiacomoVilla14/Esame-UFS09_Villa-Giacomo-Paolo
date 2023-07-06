<script>
export default {
  name: "Cart",
  props: {
    prodotto: {
      type: Object
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
  </div>
</template>

<style scoped>

</style>
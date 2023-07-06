<script>

export default {
  name: "Products",
  props: {
    titolo: {
      type: String,
      required: true
    },
    id: {
      type: Number,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    thumbn: {
      type: String,
    }
  },
  provide() {
    return {
      id: this.id
    }
  }
}
</script>

<template>
  <div class="container">
    <h3>{{ titolo }}</h3>
    <img :src="thumbn" alt="Immagine">
    <h5>{{ description }}</h5>
    <RouterLink :to="`/products/`+id">
      Dettagli
    </RouterLink>
    <button>Add to cart</button>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
  padding: 10px;
  border: 2px solid white;
  border-radius: 5px;
}

.container {
  border: solid 1px white;
  border-radius: 20px;
  padding: 20px;
  display: flex;
  flex-direction: column;
}

button {
  height: 20px;
  padding: 20px
}
</style>
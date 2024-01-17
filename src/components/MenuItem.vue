<template>
  <div class="menu-item">
    <img
      class="menu-item__image"
      :src="image.source"
      :alt="image.alt"
    />
    <div>
      <h3>{{ name }}</h3>
      <p>{{ generatedPrice }} $</p>
      <p v-if="inStock">En stock</p>
      <p v-else>En rupture de stock</p>
      <div>
        <label for="add-item-quantity">
          Quantité : {{ quantity }}
        </label>
        <input
          id="add-item-quantity"
          type="number"
        />
        <button @click="addToShoppingCart(quantity)">
          Ajouter au panier d'achat
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MenuItem",
  props: ["addToShoppingCart", "image", "inStock", "name", "quantity", "price"],
  data() {
    return {
      onSale: false
    }
  },
  computed: {
    generatedPrice() {
      return this.onSale ? (this.price * 0.9).toFixed(2) : this.price
    }
  },
  beforeMount() {
    const day = new Date().getDate()
    if (day % 2 == 0) {
      return this.onSale = true
    }
  }
}
</script>

<style>
  .menu-item {
    display: flex;
    width: 500px;
    justify-content: space-between;
    margin-bottom: 30px;
  }

  .menu-item__image {
    max-width: 300px;
  }
</style>

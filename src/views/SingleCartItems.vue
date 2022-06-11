<template>
  <div class="cardItem">
    <div class="layout">
      <div>Price : ${{ product.price }}</div>
      <div>In Cart : {{ product.quantity }}</div>
      <div>Total : ${{ totoalPrice.toFixed(2) }}</div>
    </div>
    <h3>{{ product.name }}</h3>
    <p class="category">
      <b
        ><i>{{ product.category }}</i></b
      >
    </p>
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  props: ["product"],
  computed: {
    description() {
      return this.product.description.substring(0, 120);
    },

    totoalPrice() {
      return this.product.price * this.product.quantity;
    },
  },
};
</script>

<style>
.cardItem {
  width: 600px;
  margin: 20px auto;
  padding: 3px;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(138, 107, 107, 0.498);
  text-align: start;
}
.cardItem > h3,
.category {
  text-align: center;
}
.layout {
  display: flex;
  justify-content: space-around;
  font-weight: bold;
  padding: 5px 0;
  background-color: skyblue;
}
</style>
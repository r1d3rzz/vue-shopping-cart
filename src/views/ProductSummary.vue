<template>
  <div class="productSummary card">
    <h2>{{ product.name }}</h2>
    <p>{{ product.category }}</p>
    <p>
      {{ description }}
    </p>
    <h3>${{ product.price.toFixed(2) }}</h3>
    <button class="viewBtn" @click="viewProduct(product)">View Product</button>
  </div>
</template>

<script>
export default {
  props: ["product"],
  components: {},
  computed: {
    description() {
      return this.product.description.substring(0, 100);
    },
  },

  methods: {
    viewProduct(product) {
      this.$emit("viewproduct", product);
    },
  },
};
</script>

<style>
.card {
  width: 300px;
  border: 1px solid gray;
  padding: 5px;
  border-radius: 5px;
  box-shadow: 10px 10px 10px rgba(0, 0, 0, 0.432);
  display: inline-block;
  margin: 20px;
}
.viewBtn {
  background-color: rgb(87, 113, 220);
  color: white;
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
}
</style>
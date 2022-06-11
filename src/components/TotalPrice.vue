<template>
  <div class="totalPrice cardItem">
    <h2>Total Cost : ${{ totalCost.toFixed(2) }}</h2>
    <button>Pay by Credit Card</button>
  </div>
</template>

<script>
export default {
  computed: {
    totalCost() {
      return this.$store.getters.totalPrice;
    },
  },
};
</script>

<style>
</style>
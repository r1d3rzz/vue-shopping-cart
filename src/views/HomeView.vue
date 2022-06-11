<template>
  <div class="home">
    <ProductSummary v-for="item in items" :key="item.id" :product="item" />
  </div>
</template>

<script>
import ProductSummary from "./ProductSummary.vue";
import items from "../data/items";

export default {
  name: "HomeView",
  components: { ProductSummary },
  data() {
    return {
      items,
    };
  },
};
</script>

<style scoped>
</style>

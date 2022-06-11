<template>
  <ProductDetail
    :product="product"
    :active="active.showDetail"
    @closeModel="closeModel"
  />

  <div class="home">
    <ProductSummary
      v-for="item in items"
      :key="item.id"
      :product="item"
      @viewproduct="viewproduct"
    />
  </div>
</template>

<script>
import ProductSummary from "./ProductSummary.vue";
import ProductDetail from "@/components/ProductDetail.vue";

import items from "../data/items";

export default {
  name: "HomeView",
  components: { ProductSummary, ProductDetail },
  data() {
    return {
      items,
      product: null,
      active: {
        showDetail: false,
      },
    };
  },
  methods: {
    viewproduct(product) {
      this.product = product;
      this.active.showDetail = true;
    },

    closeModel() {
      this.active.showDetail = false;
    },
  },
};
</script>

<style scoped>
</style>

<template>
  <div class="cart">
    <SingleCartItems
      v-for="product in items"
      :key="product.id"
      :product="product"
    />
    <TotalPrice />
  </div>
</template>

<script>
import SingleCartItems from "./SingleCartItems.vue";
import TotalPrice from "@/components/TotalPrice.vue";

export default {
  components: { SingleCartItems, TotalPrice },
  computed: {
    items() {
      return this.$store.getters.totalCartItems;
    },
  },
};
</script>

<style>
</style>
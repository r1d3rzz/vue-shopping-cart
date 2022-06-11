<template>
  <div
    class="sliderBackground"
    :class="{ show: active }"
    @click="closeDetail"
  ></div>

  <div class="productDetail" :class="{ show: active }">
    <div class="closeBtn">
      <span @click="closeDetail">x</span>
    </div>

    <div class="card" v-if="product">
      <h2>{{ product.name }}</h2>
      <p>{{ product.category }}</p>
      <p>
        {{ product.description }}
      </p>
      <h3>${{ product.price.toFixed(2) }}</h3>

      <div class="cart-total" v-if="totalProduct">
        <h3>In Cart : {{ totalProduct }}</h3>
      </div>

      <button>Remove</button>
      <button>Add</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["product", "active"],
  emits: ["closeModel"],
  data() {
    return {};
  },

  computed: {
    totalProduct() {
      return 52;
    },
  },

  methods: {
    closeDetail() {
      this.$emit("closeModel");
    },
  },
};
</script>

<style>
.sliderBackground {
  width: 100%;
  height: 100vh;
  background-color: rgba(128, 128, 128, 0.268);
  top: 0;
  left: 0;
  position: fixed;
  z-index: 100;
  transition: display 0.5s;
  display: none;
}

.productDetail {
  z-index: 101;
  position: fixed;
  height: 100vh;
  background-color: white;
  top: 0;
  padding: 15px;
  transition: left 0.5s;
  left: -105vw;
  overflow-y: scroll;
}

.closeBtn {
  display: flex;
  justify-content: end;
  font-size: 20px;
  font-weight: bold;
}

.closeBtn > span {
  border: 2px solid gray;
  padding: 5px;
  user-select: none;
  cursor: pointer;
}

.closeBtn > span:hover {
  color: red;
  border-color: red;
}

.show {
  left: 0;
  display: block;
}
</style>
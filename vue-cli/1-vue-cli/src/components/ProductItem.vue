<template>
  <div class="product">
    <strong>{{ productItem.title }}</strong>
    <p>{{ productItem.description }}</p>
    <strong
      >Fiyat: {{ productItem.price }} | Adet: {{ productItem.count }}</strong
    >
    <br /><br />
    <button @click="addToCart(productItem)">Sepete Ekle</button>
  </div>
</template>

<script>
export default {
  name: "ProductItem",
  props: ["productItem"],
  methods: {
    addToCart(productItem) {
      this.$emit("addToCartHandle", productItem);
    },
  },
};
</script>

<style >
.product {
  border: 2px dashed #666;
  padding: 5px 10px;
  width: 300px;
  margin-bottom: 5px;
}

.product:hover {
  border: 2px solid #666;
}
</style>

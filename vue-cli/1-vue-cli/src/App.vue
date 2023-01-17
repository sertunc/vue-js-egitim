<template>
  <div class="container">
    <div class="cart">
      <h3>Sepet</h3>
      <ul>
        <li v-for="item in cartItems" :key="item.id">{{ item.title }}</li>
      </ul>
      <p v-if="cartItems.length === 0">Sepetiniz boş.</p>
    </div>

    <product-item
      :productItem="item"
      @addToCartHandle="cartItems.push($event)"
      v-for="item in productList"
      :key="item.id"
    />
  </div>
</template>

<script>
import ProductItem from "@/components/ProductItem.vue";
export default {
  components: {
    ProductItem,
  },
  data() {
    return {
      productList: [
        {
          id: 1,
          title: "Macbook Pro",
          price: 100,
          count: 0,
          description: "Açıklama 1",
        },
        {
          id: 2,
          title: "iPhone",
          price: 50,
          count: 100,
          description: "Açıklama 2",
        },
        {
          id: 3,
          title: "Klavye",
          price: 10,
          count: 1000,
          description: "Açıklama 3",
        },
      ],
      cartItems: [],
    };
  },
};
</script>

<style >
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.cart {
  margin-bottom: 50px;
}
</style>
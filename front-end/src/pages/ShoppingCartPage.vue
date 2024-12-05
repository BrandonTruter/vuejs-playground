<template>
  <h1>Shopping Cart</h1>
  <div v-if="cartItems.length > 0">
    <ShoppingCartList :products="cartItems" />
    <button class="checkout-button">Proceed to Checkout</button>
  </div>
  <div v-if="cartItems.length === 0">
    You currently have no items in your cart!
  </div>
</template>

<script>
import { cartItems } from '../temp-data';
import ShoppingCartList from '@/components/ShoppingCartList.vue';

export default {
  name: "ShoppingCartPage",
  data() {
    return {
      cartItems
    }
  },
  components: {
    ShoppingCartList
  }
}
</script>
<template>
  <div class="nav-bar">
    <router-link to="/products" class="products-link">
      <div class="logo-wrap">
        <img :src="logo" />
      </div>
    </router-link>
    <div class="nav-buttons-wrap">
      <button @click="signOut" v-if="user">Sign Out</button>
      <router-link to="/cart">
        <button>Shopping Cart</button>
      </router-link>
    </div>

  </div>
</template>

<script>
import { getAuth, signOut } from 'firebase/auth';

export default {
  name: "NavBar",
  props: ['user'],
  methods: {
    signOut() {
      const auth = getAuth();
      signOut(auth);
    }
  }
}
</script>
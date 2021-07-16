<template>
  <div id="app">
    <div v-if="isLogin">
      <navbar :cart="cart" />
      <product-list @add="storeToCart($event)" />
    </div>
    <login 
      v-else
      :form="form"
      @submit="login($event)" />
  </div>
</template>

<script>
import Login from './components/Login.vue'
import Navbar from './components/Navbar.vue'
import ProductList from './components/ProductList.vue'

export default {
  name: 'App',
  components: {
    Login,
    Navbar,
    ProductList
  },
  data () {
    return {
      form: {
        email: '',
        password: ''
      },
      isLogin: true,
      cart: []
    }
  },
  methods: {
    login (value) {
      console.log(value)
      if (value.email === 'admin' && value.password === 'admin') {
        this.isLogin = true
      }
    },
    storeToCart (value) {
      this.cart.push(value)
    }
  }
}
</script>

<style>
  body {
    margin: 0px;
  }
</style>
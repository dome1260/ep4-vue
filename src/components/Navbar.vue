<template>
  <div class="navbar">
    <div>
      <b> Navbar </b>
    </div>
    <div>
      <div class="flex">
        <img
          :src="cartIcon"
          alt="cart-icon"
          class="img"
          @click="showData()">
        <p style="margin: 8px 0 0 20px;">
          : {{ quantity }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    cart: {
      type: Array,
      deafult: () => ([])
    }
  },
  data () {
    return {
      cartIcon: 'https://i.pinimg.com/originals/15/bb/55/15bb559cdd28f56d7c17b00498b4a946.png'
    }
  },
  computed: {
    quantity () {
      return this.cart?.length
    }
  },
  methods: {
    showData () {
      alert(JSON.stringify(this.cart))
    }
  }
}
</script>

<style scoped>
  .flex {
    display: flex;
  }
  .img {
    width: 32px;
    height: 32px;
  }
  .navbar {
    border: 1px solid black;
    padding: 16px;
    display: flex;
    justify-content: space-between;
  }
</style>
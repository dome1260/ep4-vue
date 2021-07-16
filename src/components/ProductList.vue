<template>
  <div class="product-container">
    <p>
      <b> Product </b>
    </p>
    <div class="product-list">
      <div
        v-for="(product, i) in products"
        :key="i"
        class="product">
        <img
          :src="product.src"
          alt="product-icon"
          class="img">
        <p>
          {{ product.name }}
        </p>
        <p>
          {{ product.price }}
        </p>
        <button
          class="btn"
          @click="addToCart(product)">
          Add to Cart
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductList',
  data () {
    return {
      products: [
        {
          src: 'https://www.iaumreview.com/wp-content/uploads/2021/04/iPhone-13-Product-Red.jpeg',
          name: 'A',
          price: 1000
        },
        {
          src: 'https://www.iaumreview.com/wp-content/uploads/2021/04/iPhone-13-Product-Red.jpeg',
          name: 'B',
          price: 1200
        },
        {
          src: 'https://www.iaumreview.com/wp-content/uploads/2021/04/iPhone-13-Product-Red.jpeg',
          name: 'C',
          price: 1500
        },
        {
          src: 'https://www.iaumreview.com/wp-content/uploads/2021/04/iPhone-13-Product-Red.jpeg',
          name: 'D',
          price: 1800
        },
        {
          src: 'https://www.iaumreview.com/wp-content/uploads/2021/04/iPhone-13-Product-Red.jpeg',
          name: 'E',
          price: 2100
        },
        {
          src: 'https://www.iaumreview.com/wp-content/uploads/2021/04/iPhone-13-Product-Red.jpeg',
          name: 'F',
          price: 3000
        },
        {
          src: 'https://www.iaumreview.com/wp-content/uploads/2021/04/iPhone-13-Product-Red.jpeg',
          name: 'G',
          price: 4000
        },
        {
          src: 'https://www.iaumreview.com/wp-content/uploads/2021/04/iPhone-13-Product-Red.jpeg',
          name: 'H',
          price: 5000
        }
      ]
    }
  },
  methods: {
    addToCart (value) {
      this.$emit('add', value)
    }
  }
}
</script>

<style scoped>
  .product-container {
    padding: 24px;
  }
  .product-list {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
  .product {
    width: 250px;
    padding: 24px;
    border: 1px solid black;
    margin-bottom: 20px;
  }
  .img {
    max-width: 250px;
    height: 150;
  }
  .btn {
    width: 100%;
    padding: 8px 16px;
  }
</style>
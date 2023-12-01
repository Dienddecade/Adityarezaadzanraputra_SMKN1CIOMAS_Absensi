<!-- components/ProductCard.vue -->
<template>
    <div class="product-card">
      <img :src="product.image" alt="Product Image" class="product-image" />
      <h3 class="product-name">{{ product.name }}</h3>
      <p class="product-price">${{ product.price }}</p>
      <button @click="addToCart" class="add-to-cart-btn">Add to Cart</button>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      product: {
        type: Object,
        required: true,
      },
    },
    methods: {
      addToCart() {
        // Implement logic to add product to cart
        this.$emit('add-to-cart', this.product);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Styling for ProductCard component */
  .product-card {
    border: 1px solid #ccc;
    padding: 15px;
    margin: 10px;
    text-align: center;
  }
  
  .product-image {
    max-width: 100%;
    height: auto;
  }
  
  .product-name {
    font-size: 1.2rem;
    margin: 10px 0;
  }
  
  .product-price {
    font-weight: bold;
    color: #007bff;
  }
  
  .add-to-cart-btn {
    background-color: #007bff;
    color: #fff;
    padding: 8px 15px;
    border: none;
    cursor: pointer;
  }
  </style>
  
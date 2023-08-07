<template>
    <div class="card" :class="{ sale: product.sale, outOfStock: product.outOfStock }">
      <h4>{{ title }}</h4>
      <img :src="product.image" alt="" width="70" height="70">
      <p v-if="product.sale">SALE</p>
      <p>
        {{ product.name }}
      </p>
      <p>
        {{ product.price }}
      </p>
      <button @click="openModal">Buy</button>
    </div>
  </template>
  
  <script>
    export default {
      props: ['product', 'title'],
      methods: {
        openModal() {
          this.$emit('onOpen');
        }
      }
    }
  </script>
  
  <style>
    .card {
      width: 150px;
      height: 250px;
      background-color: #ccc;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      padding: 20px;
    }
  
    .card.sale {
      background-color: #f33c3cf0;
    }
  
    .card.outOfStock {
      background-color: #f9aaaa;
    }
  </style>
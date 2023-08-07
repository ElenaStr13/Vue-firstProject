<script>
import Card from "./components/Card.vue";
import Modal from "./components/Modal.vue";

export default {
  data() {
    return {
      products: [],
      isModalOpen: false
    }
  },
  components: { Card, Modal },
  methods: {
    getProducts() {
      this.products = [
        {
          id: 1,
          name: 'Product 1',
          price: 100,
          image: 'https://picsum.photos/800',
          sale: true,
          outOfStock: true
        },
        {
          id: 2,
          name: 'Product 2',
          price: 400,
          image: 'https://picsum.photos/800',
          sale: false,
          outOfStock: false
        },
        {
          id: 3,
          name: 'Product 3',
          price: 300,
          image: 'https://picsum.photos/800',
          sale: false,
          outOfStock: true
        }
      ]
    },
    toggleModal() {
      this.isModalOpen = !this.isModalOpen;
    }
  },
  mounted() {
    this.getProducts();
  }
}
</script>

<template>
  <h1>Catalog of cards</h1>
  <nav class="menu">
    <div>One catagory</div>
    <div>Two catagory</div>
    <div>Three catagory</div>
    <div>Four catagory</div>
  </nav>
  <div class="card-wrapper">
    <Card 
      v-for="product in products" 
      :key="product.id" 
      :product="product" 
      title="Product card"
      @onOpen="toggleModal"
    />

    <Modal v-if="isModalOpen" @onClose="toggleModal"/>
  </div>
</template>

<style>
  .card-wrapper {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
  }

  .menu {
    display: flex;
    flex-direction: row;
    gap: 20px;
    margin-bottom: 20px;
  }
</style>
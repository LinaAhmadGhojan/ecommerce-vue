<template>
  <div class="banner_bg_main" style="text-align: center;    background: none;">
    <h1>Products</h1>
      <div class="row">
        <div v-for="product in products" :key="product.id" class="col-md-4">
          <div class="card mb-4 box-shadow">
            <img class="card-img-top" :src="product.image" alt="Product image">
            <div class="card-body">
              <h5 class="card-title">{{ product.name }}</h5>
              <p class="card-text">{{ product.description }}</p>
              <div class="d-flex justify-content-between align-items-center">
                <router-link :to="'/products/' + product.id" class="btn btn-sm btn-outline-secondary">View</router-link>
                <span class="text-muted">{{ product.price }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import axios from 'axios'
  
  export default {
    name: 'Products',
  
    data() {
      return {
        products: []
      }
    },
  
    mounted() {
      axios.get('https://fakestoreapi.com/products')
        .then(response => {
          this.products = response.data
        })
        .catch(error => {
          console.log(error)
        })
    }
  }
  </script>
  
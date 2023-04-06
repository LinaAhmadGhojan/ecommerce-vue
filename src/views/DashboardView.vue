<template>
 <div>
  dashboard
 </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        products: [
          { 
            id: 1,
            title: 'Product 1',
            price: '$19.99',
            image: 'https://via.placeholder.com/150',
          },
          {
            id: 2,
            title: 'Product 2',
            price: '$29.99',
            image: 'https://via.placeholder.com/150',
          },
          {
            id: 3,
            title: 'Product 3',
            price: '$39.99',
            image: 'https://via.placeholder.com/150',
          },
        ],
      };
    },
    methods: {
      addToCart(product) {
        // code to add product to cart
      },
    },
  };
  </script>
  
  <style>
  .products {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
  }
  
  .product {
    width: 250px;
    border: 1px solid #ccc;
    padding: 10px;
    text-align: center;
  }
  
  .product-image {
    width: 150px;
    height: 150px;
    object-fit: cover;
    margin: 0 auto 10px;
  }
  
  .product-title {
    font-size: 1.2rem;
    margin-bottom: 5px;
  }
  
  .product-price {
    font-size: 1.1rem;
    margin-bottom: 10px;
  }
  
  .add-to-cart-button {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 5px 10px;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .add-to-cart-button:hover {
    background-color: #0062cc;
  }
  </style>
  
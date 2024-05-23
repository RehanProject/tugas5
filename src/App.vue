<template>
    <div>
      <header class="header">
        <h1>Killers Shop</h1>
        <p>This is a shop for killers</p>
      </header>
      <div class="q-pa-md">
        <q-carousel
          swipeable
          animated
          v-model="slide"
          :autoplay="autoplay"
          ref="carousel"
          infinite
        >
          <q-carousel-slide :name="1" img-src="/images/gambar 1.jpg" />
          <q-carousel-slide :name="2" img-src="/images/gambar 2.jpg" />
          <q-carousel-slide :name="3" img-src="/images/gambar 3 .jpg" />
          <q-carousel-slide :name="4" img-src="/images/gambar 4.jpg" />
  
          <template v-slot:control>
            <q-carousel-control
              position="top-right"
              :offset="[18, 18]"
              class="text-white rounded-borders"
              style="background: rgba(0, 0, 0, .3); padding: 4px 8px;"
            >
              <q-toggle dense dark color="orange" v-model="autoplay" label="Auto Play" />
            </q-carousel-control>
  
            <q-carousel-control
              position="bottom-right"
              :offset="[18, 18]"
              class="q-gutter-xs"
            >
              <q-btn
                push round dense color="orange" text-color="black" icon="arrow_left"
                @click="$refs.carousel.previous()"
              />
              <q-btn
                push round dense color="orange" text-color="black" icon="arrow_right"
                @click="$refs.carousel.next()"
              />
            </q-carousel-control>
          </template>
        </q-carousel>
      </div>
      <section class="products">
        <div class="container">
          <div class="row">
            <div class="col-md-4" v-for="product in products" :key="product.id">
            <div class="card mb-4">
             <img class="card-img-top" :src="product.image" alt="product.image" style="width: 300px; height: 300px;">
             <div class="card-body">
            <h5 class="card-title">{{ product.name }}</h5>
            <p class="card-text">{{ product.price }}</p>
            <button @click="addToCart(product)" class="btn btn-primary">Add to Cart</button>
        </div>
    </div>
</div>

          </div>
        </div>
      </section>
      <div class="q-pa-md">
    <q-card class="my-card">
      <q-video src="https://www.youtube.com/embed/hKRUPYrAQoE?rel=0" />



      <q-card-section>
        <div class="text-h6">Killers Shop</div>
        <div class="text-subtitle2">by Rehan Panam</div>
      </q-card-section>

      <q-card-section class="q-pt-none">
        Selamat datang di "Killers Shop" - Destinasi Utama bagi Para Pencinta Senjata Api!
      </q-card-section>
    </q-card>
  </div>
  <footer>
<div class="footer">
Copyright © 2024 Rehan Tifanno 

</div>
</footer>
  </div>   
  </template>
  
  <script>
  import { ref } from 'vue'
  
  export default {
    setup() {
      const slide = ref(1)
      const autoplay = ref(false)
      return { slide, autoplay }
    },
    data() {
      return {
        products: [
          { id: 1, name: 'Pistol 1', image: '/images/gambar 5.jpg', price: 'Rp 20.000.000' }, 
          { id: 2, name: 'Pistol 2', image: '/images/gambar 6.jpg', price: 'Rp 100.000.000' },
          { id: 3, name: 'Pistol 3', image: '/images/gambar 7.jpg', price: 'Rp 300.000.000' },
          
        ]
      };
    },
    methods: {
      addToCart(product) {
        // Implement your add to cart logic here
        alert('Product added to cart: ' + product.name);
      }
    }
  
  };
  </script>
  
  <style>
  body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

.header {
  background-color: #454c52;
  color: #fff;
  text-align: center;
  padding: 20px 0;
}

.header h1 {
  margin: 0;
}

.products {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin: 20px;
}

.product {
  width: 200px;
  margin: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  text-align: center;
}

.product img {
  max-width: 100%;
  height: auto;
}

.btn {
  background-color: #333;
  color: #fff;
  border: none;
  padding: 5px 10px;
  border-radius: 3px;
  cursor: pointer;
}

.footer {
  background: #000;
  color: #fff;
  padding: 20px 0px;
  font-family: 'Play', sans-serif;
  text-align: center;
}

  </style>
  
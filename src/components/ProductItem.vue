<template>
    <v-row justify="center" class="space px-16 mx-20">
      <v-col
        cols="12"
        xs="12"
        sm="6"
        md="4"
        v-for="(product, i) in products"
        :key="i"
      >
      <v-card
            class="ma-4"
            width="100%"
          >
          <div align="center" justify="center">
            <v-img
          
              contain
              :src="product.img"
            ></v-img>
          </div>
          <v-card-title><strong>{{ product.title }}</strong></v-card-title>
          <v-card-subtitle class="descriptionShort lowOpacity">
            <strong>hihihi</strong>
          </v-card-subtitle>
          <v-card-subtitle class="descriptionShort">
            {{ product.price }}
          </v-card-subtitle>

          </v-card>
      </v-col>
    </v-row>
  </template>
  
  <script>
  export default {
    data: () => ({
        bpm: 1,
      products: [
        { img: "01.png", title: "Cabbage", subtitle: "1kg", price: "$13" },
        { img: "02.png", title: "Perry's Ice Cream", subtitle: "1kg", price: "$23" },
        { img: "3.png", title: "Potato", subtitle: "1kg", price: "$17" },
        { img: "4.png", title: "Bundle Pack", subtitle: "Potato, Papaya, Oil, Cabbage", price: "$40" },
        { img: "5.png", title: "Oreo Biscuit", subtitle: "270GM", price: "$20" },
        { img: "6.png", title: "Papaya", subtitle: "1kg", price: "$10" },
      ],
    }),
     methods: {
        decrement () {
          this.bpm--
        },
        increment () {
          this.bpm++
        },
       
      },
  };
  </script>
  
  <style>
  </style>
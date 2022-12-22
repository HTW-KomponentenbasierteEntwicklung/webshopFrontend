<template>
    <v-app>
      <NavBar />
      <v-container fluid class="paddingTop100 alignleft px-15 width50Only">
        <v-row>
           <v-col cols="lg-8">
        <v-stepper v-model="e1" alt-labels>
    <v-stepper-header>
      <v-stepper-step
        :editable="e1 > 1  && e1 < 4"
        :complete="e1 > 1"
        step="1"
      >
        Information
      </v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step
        :complete="e1 > 2"
        :editable="e1 > 2 && e1 < 4"

        step="2"
      >
        Zahlung
      </v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step :complete="e1 > 3"
        :editable="e1 > 2 && e1 < 4" step="3">
        Überprüfen
      </v-stepper-step>
      <v-divider></v-divider>

      <v-stepper-step :complete="e1 > 4"
         step="4">
        Geschafft
      </v-stepper-step>
    </v-stepper-header>

    <v-stepper-items>
      <v-stepper-content step="1">
        <CheckoutInfo />
        <v-row>
        <v-col cols="5">
          <v-btn
          large
          rounded
          dark
          color="purple"
          @click="step1"
          class="fullWidth mb-10 "
        >
          Weiter zur Zahlung
        </v-btn>
        </v-col>
      </v-row>
       

      </v-stepper-content>

      <v-stepper-content step="2">
        <PaymentInfo/>

        <v-row>
        <v-col cols="5">
          <v-btn
          large
          rounded
          dark
          color="purple"
          @click="step2"
          class="fullWidth mb-10"
        >
          Weiter zur Bestellübersicht
        </v-btn>
        </v-col>
      </v-row>
      </v-stepper-content>

      <v-stepper-content step="3">
        <CartList :cartItems="cartItems"></CartList>
        <v-divider></v-divider>
<div class="  width50 mr-10">
  <div class=" flex spaceBetween ">
    <h3>Zwischensumme</h3>
  <h3 > {{ totalSum }}</h3>
  </div>
  <div class="flex spaceBetween ">
    <h3>Versandkosten</h3>
  <h3 > {{ totalSum }}</h3>
  </div>
  <v-divider></v-divider>
  <div class="flex spaceBetween ">
    <h3>Gesamtsumme</h3>
  <h3 >150,95 €</h3>
  </div>
</div>
       
        <div class="width50 mr-10 mt-5">
          <v-btn
          large
          rounded
          dark
          color="purple"
          @click="finishCheckout"
          class="fullWidth mb-10 "
        >
          Bestellung aufgeben
        </v-btn>
        </div>
      </v-stepper-content>
      <v-stepper-content step="4">
        <div align="center">
          <h1>Vielen Dank für Ihre Bestellung!</h1>
          <h3>Ihre Bestellungsnummer lautet <a>{{ OrderNr }}</a></h3>

        </div>
      </v-stepper-content>
    </v-stepper-items>
  </v-stepper>
</v-col>
       
<v-col cols="lg-4">
  <v-card class="pa-10" v-if="e1 < 3">
    <h1>Mein Warenkorb</h1>
    <div class="mb-5">
      <u><a >Bearbeiten</a></u>

    </div>
    <v-divider></v-divider>
    <CartListNotRemovable :cartItems="cartItems"></CartListNotRemovable> 
    <v-divider></v-divider>
    <div class="mr-10">
  <div class=" flex spaceBetween ">
    <p>Zwischensumme</p>
  <h3 > {{ totalSum }}</h3>
  </div>
  <div class="flex spaceBetween ">
    <p>Versandkosten</p>
  <h3 > {{ totalSum }}</h3>
  </div>
  <v-divider></v-divider>
  <div class="flex spaceBetween ">
    <h3>Gesamtsumme</h3>
  <h1 >150,95 €</h1>
  </div>
</div>
  </v-card>
  <v-card class="pa-10" v-if="e1 === 3">
    <h1>Meine Daten</h1>
    <div class=" mt-10 flex spaceBetween ">
    <h2>Rechnungsadresse</h2>
    <v-btn icon><v-icon>mdi-pencil</v-icon></v-btn>
  </div>
    <p class="my-5">My Linh <br> Baumstr 2<br> 12345 Berlin <br><br> mylinh@hallo.com</p>
    <div class=" mt-10 flex spaceBetween ">
    <h2>Lieferadresse</h2>
    <v-btn icon><v-icon>mdi-pencil</v-icon></v-btn>
  </div>
  <p class="my-5">My Linh <br> Baumstr 2<br> 12345 Berlin <br><br> mylinh@hallo.com</p>

  <v-divider></v-divider>
  <h1 class="mt-3">Zahlungsmethode</h1>
  <div class=" mt-10 flex spaceBetween ">
    <h2>Zahlart</h2>
    <v-btn icon><v-icon>mdi-pencil</v-icon></v-btn>
  </div>
  <v-img  class="alignleft ml-5 mt-3" :aspect-ratio="16/4" width="140px" src="https://www.steiff.com/dist/paypal.svg?c15171b8d1add89d6715cbfcc015b01e"></v-img>
  </v-card>
</v-col>
</v-row>
      </v-container>
      </v-app>
</template>
<script>
  import NavBar from "../components/NavBar.vue";
  import CheckoutInfo from "../components/CheckoutInfo.vue";
import PaymentInfo from "@/components/PaymentInfo.vue";
import CartList from "@/components/CartList.vue";
import CartListNotRemovable from "@/components/CartListNotRemovable.vue";
  export default  {
    name: "checkoutView",
    data () {
      return {
        totalSum: "45.67 EURO",
        e1: 1,
        OrderNr: "1234567",
        cartItems: [
        {id:"123", img: "01.png", productName: "Crabbe Trabbe", size: "7cm", price: "45,50 €", amount: 1},
        {id: "345",img: "02.png", productName: "Crabbe Trabbe", size: "12cm", price: "45,50 €", amount: 1},
        {id:"123", img: "01.png", productName: "Crabbe Trabbe", size: "7cm", price: "45,50 €", amount: 1},
        {id: "345",img: "02.png", productName: "Crabbe Trabbe", size: "12cm", price: "45,50 €", amount: 1},
        {id:"123", img: "01.png", productName: "Crabbe Trabbe", size: "7cm", price: "45,50 €", amount: 1},
        {id: "345",img: "02.png", productName: "Crabbe Trabbe", size: "12cm", price: "45,50 €", amount: 1},
    ],
      }
    },
    components: {
    NavBar,
    CheckoutInfo,
    PaymentInfo,
    CartList,
    CartListNotRemovable,
},
methods: {
  finishCheckout:function () {
    this.e1 = 4;
    this.editable1=false;
    this.editable2= false;
    this.editable3=false;

  },
  step1: function () {
    this.e1=2;
 
  },
  step2:function () {
    this.e1 = 3;
    
  }
}
}
</script>
<style>
.paddingTop100{
    margin-top: 100px;
}
.height80{
    height: 80px;
}
.fullWidth{
  width:100%;
}
.rightAlign{
  text-align: right !important;
}
.flex{
  display: flex;
}
.spaceBetween {
  justify-content: space-between;
}
.width50Only {
  width:80%;
}
@media screen and (min-width: 62em){
  .width50 {
  width: 50%;
  margin-left: auto;
}
}

</style>
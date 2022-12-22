<template>
    <v-app>
      <NavBar />
      <v-container fluid class="paddingTop100 alignleft marginx">
        <v-row >
          <v-col cols="6">
          <div align="center" justify="center">
            <v-img

              contain
              src="01.png"
            ></v-img>
          </div>
        </v-col>
          <v-col cols="4" class="">
            <h3>Hallo, ich bin</h3>
            <h1 class="productTitle">Crabbe trabbe</h1>
            <h2>€169.00</h2>
            <div align="center" justify="center">
              <v-row>
                <v-col cols="10">
                  
                    <v-btn id="idCartButton" rounded color="purple" dark large class="my-5 bigButton" ><h2>In den Warenkorb</h2></v-btn>
                </v-col>
              <v-col cols="2">
                <v-btn
              icon
              color="black"
              x-large
              class="my-3"
            >
              <v-icon>far fa-heart</v-icon>
            </v-btn>
              </v-col>
              </v-row>
              
            </div>

            <v-divider ></v-divider>
            <Accordion>
        <AccordionItem>
          <!-- This slot will handle the title/header of the accordion and is the part you click on -->
          <template slot="accordion-trigger">
            <p class="mt-2" ><v-icon class="mr-2 opac">fa-eye</v-icon>Beschreibung</p>
          </template>
          <!-- This slot will handle all the content that is passed to the accordion -->
          <template slot="accordion-content">
            <span>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</span>
          </template>
          
        </AccordionItem>
        <AccordionItem>
          <!-- This slot will handle the title/header of the accordion and is the part you click on -->
          <template slot="accordion-trigger">
            <p class="mt-2"><v-icon class="mr-2 opac">fa-heart</v-icon>Material und Pflege</p>
          </template>
          <!-- This slot will handle all the content that is passed to the accordion -->
          <template slot="accordion-content">
            <span>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</span>
          </template>
          
        </AccordionItem>
        <AccordionItem>
          <!-- This slot will handle the title/header of the accordion and is the part you click on -->
          <template slot="accordion-trigger">
            <p class="mt-2"><v-icon class="mr-2 opac">fa-ruler</v-icon>Größenangaben</p>
          </template>
          <!-- This slot will handle all the content that is passed to the accordion -->
          <template slot="accordion-content">
            <span>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</span>
          </template>
          
        </AccordionItem>
      </Accordion>
            <v-divider></v-divider>
          </v-col>
        
        </v-row>

      </v-container>
    </v-app>
  </template>
  <script>
  import NavBar from "../components/NavBar.vue";
  import Accordion from "../components/AccordionElement.vue";
  import AccordionItem from "../components/AccordionItem";

  export default  {
    name: "ProductsView",
    data: () => ({
      toggle_exclusive: 1,
      dialog: false
    }),
    components: {
      NavBar,
      Accordion,
    AccordionItem
  }
  }
  </script>
  <style>
  .paddingTop100{
    padding-top: 100px !important;
  }
  .alignleft {
    text-align: left !important;
  }
  .marginx{
    margin-left: 10%;
  }
  .moreDetails{
    color: black !important;

  }
  .borderTopBottom {
    border-top: 1px solid grey;
    border-bottom: 1px solid red‚;
    padding-top: 5%;
    padding-bottom:5%;
  }
  .opac{
    opacity: 0.5;
  }
  .bigButton{
    width: 100%;
  }
  #idCartButton:not(.on-hover) {
    border: thin solid;
    background-color: white;
 }
   
  
  @media screen and (min-width: 375px){
    .productTitle {
    font-size: calc(32px + 24*(100vw - 375px)/ 1545);
}
  }
  @media screen and (max-width: 47.9375em){
    .productTitle {
    font-size: 1.5rem;
}
  }
  </style>
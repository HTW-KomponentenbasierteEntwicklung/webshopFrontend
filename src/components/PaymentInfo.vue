<template>
    <v-container fluid>
      <v-radio-group v-model="paymentMethod">
        <template v-slot:label>
          <h1>Zahlungsmethode</h1>
        </template>
        <v-card class="height80 pt-5 pl-10 mt-5" elevation="5">
          <v-radio value="Paypal">
          <template v-slot:label>
            <v-row>

              <v-col cols="6">
                <v-img  class="alignleft ml-5" :aspect-ratio="16/4" width="140px" src="https://www.steiff.com/dist/paypal.svg?c15171b8d1add89d6715cbfcc015b01e"></v-img>
              </v-col>
            </v-row>
          </template>
        </v-radio>
        </v-card>

        <v-card class="height80 pt-5 pl-10 mt-3" elevation="5">
        <v-radio value="Sofortüberweisung">
          <template v-slot:label>
            <v-row>

              <v-col cols="6">
                <v-img  class="alignleft ml-5" :aspect-ratio="16/5" width="120px" src="https://www.steiff.com/dist/directEbanking.svg?1873341aa3cdcd6662a9dc53661ff9bf"></v-img>
              </v-col>
            </v-row>
          </template>
        </v-radio>
      </v-card>
      </v-radio-group>
    </v-container>
  </template>

<script>
export default  {
  name: "paymentInfo",
  data: () => ({
    paymentMethod: null,
  }),
}
</script>
<style>
.height80{
  height: 80px;
}
.alignleft{
  text-align: left;
}
.alignright{
  text-align: right;
}
</style>
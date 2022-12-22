<template>
    <div>
    <v-form class="mr-10">
        <v-row>
                <v-col cols="12"><h2 class="alignLeft">Rechnungsadresse</h2></v-col>
                
            </v-row>
            <v-row class="height80">
              <v-col cols="2">
                <v-select id="idAnrede"
                :items="anrede"
                label="Anrede"
                outlined
                rounded
        ></v-select>
              </v-col>
            </v-row>
          <v-row class="height80">
            <v-col cols="6">
              <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Vorname"
                required
                rounded outlined
              ></v-text-field>  
              
            </v-col>
            <v-col cols="6">
              <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Nachname"
                required
                rounded outlined
              ></v-text-field>  
              
            </v-col>
          </v-row>
          <v-row class="height80">
            <v-col cols="12">
              <v-text-field
                v-model="name"
                :rules="nameRules"
                label="E-mail Adresse"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
          </v-row>
          <v-row class="height80">
            <v-col cols="8">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Straße"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
            <v-col cols="4">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Haus Nr."
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
          </v-row>
          <v-row class="height80">
            <v-col cols="4">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Postleitzahl"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
            <v-col cols="7">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Ort"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
          </v-row>
          <v-row class="height80">
            <v-col cols="10">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Land"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
            
          </v-row>
          <v-row class="">
            <v-col cols="10">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Telefonnummer"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
            
          </v-row>
          <v-checkbox
              v-model="shippingAdressIsMainAdress"
              label="Lieferadresse"
              hide-details
              class="height80"
            ></v-checkbox>
         <div v-if="!shippingAdressIsMainAdress">
            <v-row>
                <v-col cols="12"><h2 class="alignLeft">Lieferadresse</h2></v-col>
                
            </v-row>
            <v-row class="height80">
              <v-col cols="2">
                <v-select 
                :items="anrede"
                label="Anrede"
                outlined
                rounded
        ></v-select>
              </v-col>
            </v-row>
          <v-row class="height80">
            <v-col cols="6">
              <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Vorname"
                required
                rounded outlined
              ></v-text-field>  
              
            </v-col>
            <v-col cols="6">
              <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Nachname"
                required
                rounded outlined
              ></v-text-field>  
              
            </v-col>
          </v-row>
          <v-row class="height80">
            <v-col cols="8">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Straße"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
            <v-col cols="4">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Haus Nr."
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
          </v-row>
          <v-row class="height80">
            <v-col cols="4">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Postleitzahl"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
            <v-col cols="7">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Ort"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
          </v-row>
          <v-row >
            <v-col cols="10">
                <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Land"
                required
                rounded outlined
              ></v-text-field>  
            </v-col>
            
          </v-row>
         </div>   
          </v-form>
    </div>
</template>
<script>
export default {
    name: "checkoutInfo",
    props:{
        
    },
    data: () => ({
        shippingAdressIsMainAdress: true,
        anrede: ["Herr", "Frau"],
    })
}
</script>
<style>
.height80{
    height: 80px;
}
.alignLeft{
    text-align: left;
}
</style>
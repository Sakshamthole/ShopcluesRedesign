<!-- This is the page to populate order summary details. -->
<template>
   <v-card  style=" background:white; box-shadow: 0 0 ; height:84%; border-radius:0px">
      <v-row>
         <!-- This is loop to iterate over items proceeded for checkout/purchase. -->
         <v-col sm="12"
            v-for="product in products"
            :key="product.title"          
            >
            <!-- for loop to display the the cards-->
            <v-row dense>
               <v-col lg="2" md="2" sm="3"  offset-sm="0">
                  <v-card style="background:white; color: black;box-shadow: 0 0 ; padding-left:10px">
                     <v-img :src="product.src" style="border: 3px solid grey;">
                     </v-img>
                  </v-card>
               </v-col>
               <!-- offset-sm="2" will shift the column by 2 in sm screen
                    sm="5" will allot 5 columns for the content in case of sm screen
                    md="6" will allot 6 columns for the content in case of md screen
                    lg="6" will allot 6 columns for the content in case of lg screen
                    offset-md="0" is added as we dont want to shift the content in case of md screen and above-->
               <v-col lg="6" md="6" sm="5" offset-sm="2" offset-md="0" style="background:white;box-shadow: 0 0 ;">
                  <v-card v-text="product.title" style="background:white; color: darkslategrey ;box-shadow: 0 0 ;font-size:18px"></v-card>
                  <v-card v-text="product.cod" style="background:white; color: darkslategrey; box-shadow: 0 0 ;font-size:16px"></v-card>
               </v-col>
               <v-col lg="2" md="2" sm="3" offset-md="0" offset-sm="1">
                  <v-card style="background:white; color: darkslategrey;box-shadow: 0 0 ;">
                     <v-btn icon style="background:white; color:grey">
                        <v-icon>mdi-minus-circle</v-icon>
                     </v-btn>
                     {{product.quantity}}
                     <v-btn icon style="background:white; color:grey">
                        <v-icon>mdi-plus-circle</v-icon>
                     </v-btn>
                  </v-card>
                  <v-card style="background:white; color: blue;box-shadow: 0 0 ; font-size:14px"> Remove </v-card>
                  <v-card style="background:white; color: blue;box-shadow: 0 0 ; font-size:14px"> Save for later </v-card>
               </v-col>
               <v-col lg="2" md="2" sm="3" offset-md="0" offset-sm="1">
                  <v-card style="background:white; color: darkslategrey;box-shadow: 0 0 ; font-size:16px">Price: <b style="color:black">{{product.price}}</b></v-card>
                  <v-card style="background:white; color: darkslategrey;box-shadow: 0 0 ; font-size:16px"> Shipping: <b style="color:black">{{product.shipping}} </b> </v-card>
               </v-col>
            </v-row>
            <hr style="margin-top:15px">
         </v-col>
      </v-row>
      </v-col>
      </v-row>
      <!-- This is the code to display order cost total and summary. -->
      <v-card style="background:white; color: darkslategrey; box-shadow: 0 0 ;width:100%">
         <v-row>
            <v-col lg="3" md="3" sm="5" style="margin-top: 30px">
               <v-card style="background:white; color: darkslategrey; box-shadow: 0 0 ;">
                  <v-btn icon style="background:white; color: darkslategrey; box-shadow: 0 0 ;">
                     <v-icon>mdi-map-marker-outline</v-icon>
                  </v-btn>
                  Delivery Pincode
               </v-card>
               <v-card style="background:white; color: darkslategrey; box-shadow: 0 0 ; margin-left: 35px ; display: inline-flex">
                  431001
                  <p style="color: blue; padding-left: 20px">Change</p>
               </v-card>
            </v-col>
            <v-col lg="2" md="3" offset-md="6" sm="4" offset-sm="3" style="margin-top: 30px;" >
               <v-row style="background:white; color: black; box-shadow: 0 0 ;">
                  <v-col sm="7" style="padding:0px">Total </v-col>
                  <v-col sm="4" style="padding:0px"> Rs 6798  </v-col>
                  <v-col sm="7" style="padding:0px; margin-top:10px"><b style="font-size:20px">Grand Total </b></v-col>
                  <v-col sm="4" style="padding:0px; margin-top:10px"> <b> Rs 6798</b> </v-col>
                  <p style="font-size:10px"> Inclusive of all the applicable taxes</p>
                  <v-btn large color="white" style="background:linear-gradient(to right, orange, red);font-size:18px; padding:20px 40px; text-transform: none;" text @click="dialog = false">Place Order</v-btn>
               </v-row>
            </v-col>
         </v-row>
      </v-card>
   </v-card>
</template>
<script>
   export default {
     data: () => ({
       products: [
         { title: 'Kookaburra Kahuna 150 English Willow Bat', src: 'bat.jpg', price: 'Rs. 6399', cod:  'COD not available ', shipping: 'FREE', quantity: '1'},
         { title: 'Soft Fit Cricket Batting Gloves', src: "Gloves.jpg",price: 'Rs. 399', cod:  'COD available ', shipping: 'FREE', quantity: '1'}, 
       ],
     }),
   }
</script>
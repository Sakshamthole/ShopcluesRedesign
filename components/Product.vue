<!-- This is the page to populate order summary details. 
It contains product detail of each individual product as well as the total order summary. -->
<template>
   <v-card  style=" background:white; box-shadow: 0 0 ; border-radius:0px">
      <v-row>
         <!-- This is loop to iterate over items proceeded for checkout/purchase. -->
         <v-col cols="12" sm="12"
            v-for="product in products"
            :key="product.title"          
            >
            <!-- for loop to display the the cards-->
            <v-row dense>
               <v-col cols="3" lg="2" md="2" sm="3" offset-sm="0">
                  <v-card style="background:white; color: black;box-shadow: 0 0 ; padding-left:10px">
                     <v-img :src="product.src" style="border: 2px solid grey;">
                     </v-img>
                  </v-card>
               </v-col>
               <!-- offset-sm="2" will shift the column by 2 in sm screen
                  sm="5" will allot 5 columns for the content in case of sm screen
                  md="6" will allot 6 columns for the content in case of md screen
                  lg="6" will allot 6 columns for the content in case of lg screen
                  offset-md="0" is added as we dont want to shift the content in case of md screen and above.
                  cols is used for rendering on xs screens as xs is deprecated. 
                  So cols="7" will allot 7 columns for the content in case of xs screen-->
               <v-col cols="7" offset="1" lg="6" md="6" sm="5" offset-sm="2" offset-md="0" style="background:white;box-shadow: 0 0 ;">
                  <v-card v-text="product.title" style="background:white; color: darkslategrey ;box-shadow: 0 0 ;font-size:18px"></v-card>
                  <v-card v-text="product.cod" style="background:white; color: darkslategrey; box-shadow: 0 0 ;font-size:16px"></v-card>
               </v-col>
               <v-col cols="6" lg="2" md="2" sm="3" offset-md="0" offset-sm="1">
                  <v-card style="background:white; color: darkslategrey;box-shadow: 0 0 ;">
                     <v-btn icon style="background:white; color:grey">
                     <!-- mdi-minus-circle, mdi-plus-circle are mdi icons for a filled - and + symbol. -->
                        <v-icon>mdi-minus-circle</v-icon>
                     </v-btn>
                     {{product.quantity}}
                     <v-btn icon style="background:white; color:grey">
                        <v-icon>mdi-plus-circle</v-icon>
                     </v-btn>
                  </v-card>
                  <v-card style="background:white; color: #2874F0;box-shadow: 0 0 ; font-size:14px; padding-left:10px"> Remove </v-card>
                  <v-card style="background:white; color: #2874F0;box-shadow: 0 0 ; font-size:14px; padding-left:10px"> Save for later </v-card>
               </v-col>
               <v-col cols="6" lg="2" md="2" sm="3" offset-md="0" offset-sm="1">
                  <v-card style="background:white; color: darkslategrey;box-shadow: 0 0 ; font-size:16px">Price: <b style="color:black">{{product.price}}</b></v-card>
                  <v-card style="background:white; color: darkslategrey;box-shadow: 0 0 ; font-size:16px"> Shipping: <b style="color:black">{{product.shipping}} </b> </v-card>
               </v-col>
            </v-row>
            <hr style="margin-top:15px">
         </v-col>
         <!-- This is the code to display the delivery pincode details. -->
         <v-col cols="11" lg="3" md="3" sm="4" offset="2" offset-sm="0" offset-md="2" style="margin:0px 15px">
            <v-row style="background:white; color: darkslategrey; box-shadow: 0 0 ;margin:0px; padding:0px">
               <v-col cols="3" md="2" style="padding:0px">
                  <v-btn icon style="background:white; color: darkslategrey; box-shadow: 0 0 ;padding:0px;">
                     <v-icon style="font-size:35px">mdi-map-marker-outline</v-icon>
                  </v-btn>
               </v-col>
               <v-col cols="8" style="padding:0px"> Delivery Pincode</v-col>
               <v-col cols="5" md="4" style="padding:5px 0px">431001</v-col>
               <v-col cols="5"  md="4" style="color: #2874F0; padding:5px 0px" >  Change  </v-col>
               <v-col cols="12" class="hidden-sm-and-up">
                  <hr>
               </v-col>
            </v-row>
         </v-col>
         <v-col cols="1" sm="3" md="6"></v-col>
         <!-- This is the code to display order cost total and summary. -->
         <v-col cols="11" lg="2" md="2" sm="4" style="margin-left:15px">
            <v-row style="background:white; color: black; box-shadow: 0 0 ;">
               <v-col cols="4" offset="1"  sm="7" md="5" style="padding:0px">Total </v-col>
               <v-col cols="7" sm="4" md="6" style="padding:0px"> Rs 6798  </v-col>
               <v-col cols="4" offset="1" sm="7" md="5" style="padding:0px; margin-top:10px"><b style="font-size:20px">Grand Total </b></v-col>
               <v-col cols="7" sm="4" md="6" style="padding:0px; margin-top:10px"> <b> Rs 6798</b> </v-col>
               <v-col cols="12" offset="1" style="padding:0px;">
                  <p style="font-size:10px;padding:0px; margin:0px"> Inclusive of all the applicable taxes</p>
               </v-col>
               <v-col cols="12">
               <!-- This button is to the button to place the final order.
               linear-gradient(to right, orange, red) renders the button in gradient form from orange to red/ -->
                  <v-btn large color="white" style="background:linear-gradient(to right, orange, red);font-size:18px; padding:20px 40px;text-transform: none; width:100%" elevation="2" text @click="dialog = false">Place Order</v-btn>
               </v-col>
            </v-row>
         </v-col>
      </v-row>
   </v-card>
</template>
<!-- products data contains the list of items that the customer wants to place order for. 
This can then be rendered / displayed using a loop and thus making an object like this makes it easy to display details. -->
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
<!-- This is the page to populate order summary details. -->
<template >
   <v-card  style="margin: 17px 15px; background:white; box-shadow: 0 0 ;">
      <v-row>
      <!-- This is loop to iterate over items proceeded for checkout/purchase. -->
         <v-col md="12"
            v-for="product in products"
            :key="product.title"          
            >
            <!-- for loop to display the the cards-->
            <v-row dense>
               <v-col md="2">
                  <v-card style="background:white; color: black;box-shadow: 0 0 ; padding-left:10px">
                     <v-img
                        :src="product.src"
                        >
                     </v-img>
                  </v-card>
               </v-col>
               <v-col md="6" style="background:white; color: black;box-shadow: 0 0 ;">
                  <v-card v-text="product.title" style="background:white; color: black ;box-shadow: 0 0 ;"></v-card>
                  <v-card v-text="product.cod" style="background:white; color: black; box-shadow: 0 0 ;"></v-card>
               </v-col>
               <v-col md="2">
                  <v-card style="background:white; color: black;box-shadow: 0 0 ;">
                     <v-btn icon style="background:white; color: black">
                        <v-icon>mdi-minus-circle-outline</v-icon>
                     </v-btn>
                     {{product.quantity}}
                     <v-btn icon style="background:white; color: black">
                        <v-icon>mdi-plus-circle-outline</v-icon>
                     </v-btn>
                  </v-card>
                  <v-card style="background:white; color: black;box-shadow: 0 0 ;"> Remove </v-card>
                  <v-card style="background:white; color: black;box-shadow: 0 0 ;"> Save for later </v-card>
               </v-col>
               <v-col md="2">
                  <v-card style="background:white; color: black;box-shadow: 0 0 ;">Price: <b>{{product.price}}</b></v-card>
                  <v-card style="background:white; color: black;box-shadow: 0 0 ;"> Shipping: <b>{{product.shipping}} </b> </v-card>
               </v-col>
            </v-row>
            <hr>
         </v-col>

         <!-- This is the code to display order cost total and summary. -->
         <v-col md="3" style="margin-top: 30px">
            <v-card style="background:white; color: black; box-shadow: 0 0 ;">
               <v-btn icon style="background:white; color: black; box-shadow: 0 0 ;">
                  <v-icon>mdi-map-marker-outline</v-icon>
               </v-btn>
               Delivery Pincode
            </v-card>
            <v-card style="background:white; color: black; box-shadow: 0 0 ; margin-left: 35px ; display: inline-flex">
               431001
               <p style="color: blue; padding-left: 20px">Change</p>
            </v-card>
         </v-col>
         <v-col md="2" offset-md="7" style="margin-top: 30px">
            <v-card style="background:white; color: black; box-shadow: 0 0 ;">
               <p>Total: Rs. 6798  </p>
               <b style="font-size:20px">Grand Total: Rs 6798</b>
               <p style="font-size:10px"> Inclusive of all the applicable taxes</p>
               <v-btn large  color="white" style="background:red;font-size:20px; padding=20px" text @click="dialog = false">Place Order</v-btn>
            </v-card>
         </v-col>
      </v-row>
   </v-card>
</template>
<script>
   export default {
     data: () => ({
       products: [
         { title: 'Kookaburra Kahuna 150 English Willow Bat', src: 'bat.jpg', price: 'Rs. 6399', cod:  'COD not avaialble ', shipping: 'FREE', quantity: '1'},
         { title: 'Soft Fit Cricket Batting Glovess', src: "Gloves.jpg",price: 'Rs. 399', cod:  'COD avaialble ', shipping: 'FREE', quantity: '1'}, 
       ],
     }),
   }
</script>
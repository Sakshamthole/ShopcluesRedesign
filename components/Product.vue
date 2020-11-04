<!-- This is the page to populate order summary details. 
   It contains product detail of each individual product as well as the total order summary. -->
<template>
   <v-card  class="background-white removeBoxShadow br-0">
      <v-row>
         <!-- This is loop to iterate over items proceeded for checkout/purchase. -->
         <v-col cols="12" sm="12"
            v-for="product in products"
            :key="product.title"          
            >
            <!-- for loop to display the the cards-->
            <v-row dense>
               <v-col cols="3" lg="2" md="2" sm="3" offset-sm="0">
                  <v-card class="pa-0 pl-5 background-white removeBoxShadow" style="color: black;">
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
               <v-col cols="7" offset="1" lg="6" md="6" sm="5" offset-sm="2" offset-md="0" class="background-white removeBoxShadow">
                  <v-card v-text="product.title" class="background-white removeBoxShadow" style="color: darkslategrey ;font-size:18px"></v-card>
                  <v-card v-text="product.cod" class="background-white removeBoxShadow" style="color: darkslategrey; font-size:16px"></v-card>
               </v-col>
               <v-col cols="6" lg="2" md="2" sm="3" offset-md="0" offset-sm="1">
                  <v-card class="background-white removeBoxShadow" style="color: darkslategrey;">
                     <!-- The function decrement will decrease the quantity of the purchased product by 1 each time clicked.
                        Its minimum value can be 1 and it will not decrease beyond that. -->
                     <v-btn icon v-on:click="product.quantity=decrement(product.quantity)" class="background-white" style="color:grey">
                        <!-- mdi-minus-circle, mdi-plus-circle are mdi icons for a filled - and + symbol. -->
                        <v-icon>mdi-minus-circle</v-icon>
                     </v-btn>
                     {{product.quantity}}
                     <!-- The function increment will increase the quantity of the purchased product by 1 each time clicked. -->
                     <v-btn icon v-on:click="product.quantity=increment(product.quantity)" class="background-white" style="color:grey">
                        <v-icon>mdi-plus-circle</v-icon>
                     </v-btn>
                  </v-card>
                  <!-- The function removeProduct will remove the selected product from the cart. -->
                  <v-card class="pl-3 background-white removeBoxShadow" style="color: #2874F0; font-size:14px"  v-on:click="removeProduct(product)"> Remove </v-card>
                  <v-card class="pl-3 background-white removeBoxShadow" style="color: #2874F0; font-size:14px"> Save for later </v-card>
               </v-col>
               <v-col cols="6" lg="2" md="2" sm="3" offset-md="0" offset-sm="1">
                  <!-- The function productPrice calculates the price by multiplying the price of 1 item and the quantity.-->
                  <v-card class="background-white removeBoxShadow" style="color: darkslategrey; font-size:16px">Price: <b style="color:black">Rs. {{productPrice(product.price, product.quantity)}}</b></v-card>
                  <v-card class="background-white removeBoxShadow" style="color: darkslategrey; font-size:16px"> Shipping: <b style="color:black">{{product.shipping}} </b> </v-card>
               </v-col>
            </v-row>
            <hr class="mt-5">
         </v-col>
         <!-- This is the code to display the delivery pincode details. -->
         <v-col cols="11" lg="3" md="3" sm="4" offset="2" offset-sm="0" offset-md="2" class="my-0 mx-5">
            <v-row color="background-white removeBoxShadow" style="color: darkslategrey; margin:0px; padding:0px">
               <v-col cols="3" md="2" class="pa-0">
                  <v-icon color="background-white" style="color: darkslategrey; font-size:35px">mdi-map-marker-outline</v-icon>
               </v-col>
               <v-col cols="8" class="pa-0"> Delivery Pincode</v-col>
               <v-col cols="5" md="4" class="px-0 py-1">431001</v-col>
               <v-col cols="5"  md="4" class="px-0 py-1" style="color: #2874F0;" >  Change  </v-col>
               <v-col cols="12" class="hidden-sm-and-up">
                  <hr>
               </v-col>
            </v-row>
         </v-col>
         <v-col cols="1" sm="3" md="6"></v-col>
         <!-- This is the code to display order cost total and summary. -->
         <v-col cols="11" lg="2" md="2" sm="4" class="ml-5">
            <v-row class="background-white removeBoxShadow" style="color: black;">
               <v-col cols="4" offset="1"  sm="7" md="5" class="pa-0">Total </v-col>
               <v-col cols="7" sm="4" md="6" class="pa-0"> Rs {{totalPrice()}}  </v-col>
               <v-col cols="4" offset="1" sm="7" md="5" class="pa-0"><b style="font-size:19px">Grand Total </b></v-col>
               <v-col cols="7" sm="4" md="6" class="pa-0"> <b> Rs {{totalPrice()}} </b> </v-col>
               <v-col cols="12" offset="1" class="pa-0">
                  <p class="pa-0 ma-0" style="font-size:10px"> Inclusive of all the applicable taxes</p>
               </v-col>
               <v-col cols="12">
                  <!-- This button is to the button to place the final order.
                     linear-gradient(to right, orange, red) renders the button in gradient form from orange to red/ -->
                  <v-btn large color="white" class="px-15 py-5" style="background:linear-gradient(to right, orange, red);font-size:18px; text-transform: none; width:100%" elevation="2" text @click="dialog = false">Place Order</v-btn>
               </v-col>
            </v-row>
         </v-col>
      </v-row>
   </v-card>
</template>
<!-- products data contains the list of items that the customer wants to place order for. 
   This can then be rendered / displayed using a loop and thus making an object like this makes it easy to display details. 
   Several functions are defined to make the website reactive.-->
<script>
   export default {
     data: () => ({
       products: [
         { title: 'Kookaburra Kahuna 150 English Willow Bat', src: 'bat.jpg', price: '6399', cod:  'COD not available ', shipping: 'FREE', quantity: '1'},
         { title: 'Soft Fit Cricket Batting Gloves', src: "Gloves.jpg",price: '399', cod:  'COD available ', shipping: 'FREE', quantity: '2'}, 
       ],
     }),
   methods: {
      productPrice: function (price, quantity) {
         return parseInt(price) * parseInt(quantity);
      },
      totalPrice: function (){
         var sum = 0
         for (var i=0; i< this.products.length; i++){
            sum += parseInt(this.products[i].price) * parseInt(this.products[i].quantity);
            }
            return sum
      },
      increment: function(quantity){
         return parseInt(quantity) + 1
      },
      decrement: function(quantity){
         return parseInt(quantity) > 1 ? parseInt(quantity) - 1 : 1
      },
      
      removeProduct: function(product){
         this.products.splice(this.products.indexOf(product), 1);
      },
   },
   }
</script>
<style>
   .removeBoxShadow{
   box-shadow: 0 0 !important
   }
   .br-0{
   border-radius: 0px !important
   }
   .background-white{
   background : white !important
   }
</style>
<!-- This is the code to display apply coupons dialog box. -->
<template>
   <v-card style="background:white;">
      <v-row dense>
         <v-col md="12" sm="12">
            <h1  style="padding-left:25px;background:white; color: black;box-shadow: 0 0 ;"> My Cart (1 Item) </h1>
            <hr  style="background:white">
            <v-dialog v-model="dialog" max-width="760px">
               <!-- stays even when clicked outside the window--> 
               <template v-slot:activator="{ on, attrs }" style="background:white;color:green; width: 100%; ">
                  <v-btn
                     style="background:white;color:green;width: 100%; box-shadow: 0 0 ;"
                     dark
                     v-bind="attrs"
                     v-on="on"
                     >
                     2 offers applicable on this order     >
                  </v-btn>
               </template>
               <v-card>
                  <v-card-title>
                     <span class="headline">Available Coupons</span>
                  </v-card-title>
                  <radio/>
               </v-card
                  >
               <v-card-actions>
               <v-spacer></v-spacer>
               <v-btn color="white" text @click="dialog = false">Apply Coupon</v-btn>
               </v-card-actions   
   </v-card>
   </v-dialog>
   <hr  style="background:white">
   </v-col>
   </v-row>
   </v-card>
</template>
<!-- This is the code to display apply coupons dialog box. -->
<template>
   <v-card style="background:white; border-radius:0px">
      <v-row dense>
         <v-col md="12" sm="12">
            <h2  class="pa-0 pl-2 ma-0" style="background:white; color: black;box-shadow: 0 0 ;"> My Cart </h2>
            <hr>
            <v-dialog max-width="760px"> 
               <template v-slot:activator="{ on, attrs }" style="background:white;color:green; width: 100%; ">
                  <!-- These is the button which opens up Coupon code dialog box. -->
                  <v-btn class="pa-0 pl-2 ma-0" style="background:white;color:green; box-shadow: 0 0 ; text-transform: none; "
                     dark
                     v-bind="attrs"
                     v-on="on"
                     >
                     2 offers applicable on this order     >
                  </v-btn>
               </template>
               <v-card style="background:white; color:black; box-shadow: 0 0 ;">
                  <v-card-title>
                     <span class="headline" color="black">Available Coupons</span>
                  </v-card-title>
                  <!-- These is the search box using which you can lookup for a Coupon code. -->
                  <v-card style="background:lightgrey;color:darkslategrey; box-shadow: 0 0 ; border-radius:0px; padding:20px 10px">
                     <input type="text" style="width:50%; color: darkslategrey; outline:0; border-bottom: 2px solid black; margin-left: 25%;" placeholder="Enter Coupon Code"></input>
                  </v-card>
                  <CouponCodeList/>
               </v-card>
               <hr>
               <v-card-actions style="background:white;">
               <!-- linear-gradient(to right, orange, red) renders the button in gradient form from orange to red. -->
                  <v-btn color="white" elevation="2" style="background:linear-gradient(to right, orange, red);font-size:16px; padding:20px 40px; text-transform: none; margin-left:30%; width:40%" text @click="dialog = false">Apply Coupon</v-btn>
               </v-card-actions>
            </v-dialog>
            <hr  style="background:white">
         </v-col>
      </v-row>
   </v-card>
</template>
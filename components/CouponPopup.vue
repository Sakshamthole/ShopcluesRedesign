<!-- This is the code to display apply coupons dialog box. -->
<template>
   <v-card style="background:white; border-radius:0px">
      <v-row dense>
         <v-col md="12" sm="12">
            <h1  style="padding-left:25px;background:white; color: black;box-shadow: 0 0 ; margin:10px 0px"> My Cart (1 Item) </h1>
            <hr  style="background:white">
            <v-dialog v-model="dialog" max-width="760px">
               <!-- stays even when clicked outside the window--> 
               <template v-slot:activator="{ on, attrs }" style="background:white;color:green; width: 100%; ">
                  <v-btn
                     style="background:white;color:green; box-shadow: 0 0 ; margin-left:10px; padding:25px 0px"
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
                  <v-card style="background:lightgrey;color:darkslategrey; box-shadow: 0 0 ; border-radius:0px; padding:20px 10px">
                     <input type="text" style="width:30%; color: darkslategrey; outline:0; border-bottom: 2px solid black; margin-left: 35%;" placeholder="Enter Coupon Code"></input>
                     <!-- This is the search icon. -->
                  </v-card>
                  <radio/>
               </v-card>
               <hr>
               <v-card-actions style="background:white;">
                  <v-btn color="white" elevation="2" style="background:linear-gradient(to right, orange, red);font-size:16px; padding:20px 40px; text-transform: none; margin-left:30%; width:40%" text @click="dialog = false">Apply Coupon</v-btn>
               </v-card-actions>  
            </v-dialog>
         <hr  style="background:white">
      </v-col>
      </v-row>
   </v-card>
</template>
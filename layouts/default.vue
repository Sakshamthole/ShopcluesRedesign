<!-- This is the main default layout page. -->
<template>
   <!--Your App Starts Here -->
   <v-app id="inspire">
      <!-- This is the header bar. -->
      <v-card>
         <v-toolbar style="background:#ACE0E5">
               <v-img max-width="140px" src="logo1.png" style=" box-shadow: 0 0" elevation-0></v-img>
            <v-spacer></v-spacer>
            <v-card class="hidden-xs-only" style="background:white;color:#00A4B4; display: inherit;width: 50% ;height:60% ; box-shadow: 0 0 ; margin-left:10px; border-radius:0px">
               <input type="text" style="width:100%; color: black; outline:none; padding-left:10px" placeholder="Search for product"></input>
               <!-- This is the search icon. -->
               <v-btn icon color="#00A4B4" style="margin-top: -9px">
                  <v-icon>mdi-magnify</v-icon>
               </v-btn>
            </v-card>
            <v-spacer></v-spacer>
            <!-- These are the list of icons. -->
            <v-icon color="#00A4B4" style="padding:3px; cursor:pointer;">mdi-map-marker-outline</v-icon>
            <v-icon color="#00A4B4" style="padding:3px; cursor:pointer;">mdi-bell-outline</v-icon>
            <v-icon color="#00A4B4" style="padding:3px; cursor:pointer;">mdi-heart-outline</v-icon>
            <v-icon color="#00A4B4" style="padding:3px; cursor:pointer;">mdi-cart-outline</v-icon>
            <p style="margin-top: 15px; padding: 0px; cursor:pointer; color:black" class="hidden-sm-and-down">
               Hi ABC 
               <v-icon style="padding:0px" color="#00A4B4">mdi-menu-down</v-icon>
            </p>
                     <!-- This menu bar is to display  the title only for sm and xs screens -->
            <v-menu style="background:#ACE0E5;padding:0px; margin:0px">
               <template v-slot:activator="{ on, attrs }">
                  <v-btn style="padding:0px; margin:0px"
                     icon
                     v-bind="attrs"
                     v-on="on"
                     >
                     <v-icon color="#00A4B4" class="hidden-md-and-up" style="margin:0px;padding:0px">mdi-dots-vertical</v-icon>
                  </v-btn>
               </template>
               <p style="background:lightblue; padding: 0px 0px 0px 15px; color:black; margin:0px">
                  Hi ABC 
                  <v-btn icon color="#00A4B4">
                     <v-icon style="padding:0px; color: black">mdi-menu-down</v-icon>
                  </v-btn>
               </p>
               <v-list style="background:lightblue; color:black">
                  <v-list-item
                     v-for="item in menu"
                     >
                     <v-list-item-title style="color:black">{{ item.title }}</v-list-item-title>
                  </v-list-item>
               </v-list>
            </v-menu>
         </v-toolbar>
         <v-card class="hidden-sm-and-up" style="background:white;color:#00A4B4; display: inherit; box-shadow: 0 0 ; border-radius:0px">
            <input type="text" style="width:85%; color: black; outline:none; padding-left:10px" placeholder="Search for product"></input>
            <!-- This is the search icon. -->
            <v-btn icon color="#00A4B4">
               <v-icon>mdi-magnify</v-icon>
            </v-btn>
         </v-card>         
      </v-card>
      <!-- This menu bar is to display  the title only for md and above screens -->
      <v-card tile class="hidden-sm-and-down">
         <v-toolbar dense color="#00A4B4">
            <v-toolbar-items>
               <v-btn style="box-shadow: 0 0 ;font-size:12px" color="#00A4B4"
                  v-for="item in menu"
                  :to="item.link"
                  >{{ item.title }}</v-btn>
            </v-toolbar-items>
         </v-toolbar>
      </v-card>
      <v-card style="background:#D3EAEC; padding:10px; height:100%">
         <CouponPopup/>
         <Product/>
      </v-card>
   </v-app>
</template>
<script>
   export default {}
</script>
<style> 
   .white--text {
   border: 1px solid;
   }
   #inspire {
   background-color: white;
   color: black;
   }
</style>
<!-- This is the script to include title list in header. -->
<script>
   export default {
     data: () => ({
       menu: [
         { title: 'Made in India' },
         { title: 'Men' },
         { title: 'Women' },
         { title: 'Home & Furniture' },
         { title: 'Electronics' },
         { title: 'Appliances' },
         { title: 'Sports & More' },
         { title: 'Daily Essentials' }
        //change column width using flex 
       ],
     }),
   }
</script>
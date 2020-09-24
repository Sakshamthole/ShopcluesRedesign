<!-- This is the main default layout page. -->
<template background="black">
   <!--Your App Starts Here -->
   <v-app id="inspire" background="black">
   <!-- This is the header bar. -->
      <v-card flat tile>
         <v-toolbar dense color="cyan">
            <v-card>
               <v-img width="175px" src="logo.png"></v-img>
            </v-card>
            <v-spacer></v-spacer>
            <v-card style="background:white; display: inherit;width: 50% ;height:80% ; box-shadow: 0 0 ">
               <v-text-field color="cyan" ></v-text-field>
               <!-- This is the search icon. -->
               <v-btn icon color="cyan">
                  <v-icon>mdi-magnify</v-icon>
               </v-btn>
            </v-card>
            <v-spacer></v-spacer>
            <!-- These are the list of icons. -->
            <v-btn icon>
               <v-icon>mdi-map-marker-outline</v-icon>
            </v-btn>
            <v-btn icon>
               <v-icon>mdi-bell-outline</v-icon>
            </v-btn>
            <v-btn icon>
               <v-icon>mdi-heart-outline</v-icon>
            </v-btn>
            <v-btn icon>
               <v-icon>mdi-cart-outline</v-icon>
            </v-btn>
            <p style="margin-top: 15px; margin-left:10px; padding: 0px">
               Hi ABC 
               <v-btn icon>
                  <v-icon style="padding:0px">mdi-menu-down</v-icon>
               </v-btn>
            </p>
         </v-toolbar>
      </v-card>
      <v-card tile>
         <v-toolbar dense color="blue">
            <v-spacer></v-spacer>
            <v-toolbar-items>
               <v-btn style="box-shadow: 0 0 ;" color="blue"
                  v-for="item in menu"
                  :key="item.icon"
                  :to="item.link"
                  flat
                  >{{ item.title }}</v-btn>
            </v-toolbar-items>
         </v-toolbar>
      </v-card>
      <v-card style="background:lightblue">
         <CouponPopup/>
         <Productcopy/>
         <!--<BorderRad/>-->
        
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
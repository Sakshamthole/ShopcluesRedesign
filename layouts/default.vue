<!-- This is the main default layout page. -->
<template>
   <!--Your App Starts Here -->
   <v-app>
      <!-- This is the header. -->
      <v-card class="br-0">
         <v-toolbar class="background-ACE0E5">
            <!-- This is the company logo. -->
            <v-img max-width="140px" src="logo1.png" class="removeBoxShadow" elevation-0></v-img>
            <v-spacer></v-spacer>
            <v-card class="hidden-xs-only removeBoxShadow br-0" style="background:white; display: inherit;width: 50% ;height:60% ;">
               <input type="text" class="pl-2" color="black" style="width:100%; outline:none;" placeholder="Explore The Beyond"></input>
               <!-- This is the search icon. -->
               <v-icon color="#00A4B4" class="mr-2 cursorPointer">mdi-magnify</v-icon>
            </v-card>
            <v-spacer></v-spacer>
            <!-- These are the list of icons. -->
            <v-icon color="#00A4B4" class="pa-1 cursorPointer">mdi-map-marker-outline</v-icon>
            <v-icon color="#00A4B4" class="pa-1 cursorPointer">mdi-bell-outline</v-icon>
            <v-icon color="#00A4B4" class="pa-1 cursorPointer">mdi-heart-outline</v-icon>
            <v-icon color="#00A4B4" class="pa-1 cursorPointer">mdi-cart-outline</v-icon>
            <!-- The user account details have to be loaded from a clickable dropdown in case of sm and smaller screens.
               So class="hidden-sm-and-down" is added is to hide for sm and smaller screens. 
               It will be visible for all screens md and larger than md. 
               This menu lists down the user specific drop down items.
               -->          
            <v-menu class="background-ACE0E5">
               <template v-slot:activator="{ on, dropdownMenu }">
                  <!-- ma-0 and pa-0 are classes to add margin and padding respectively. 
                     Other classes are defined in style tag to render specific styles.-->
                  <v-btn class="ma-0 pa-1 hidden-sm-and-down background-ACE0E5 cursorPointer color-black removeBoxShadow"                     
                     v-bind="dropdownMenu"
                     v-on="on"
                     >
                     Hi ABC 
                     <v-icon class="pa-0" color="#00A4B4">mdi-menu-down</v-icon>
                  </v-btn>
               </template>
               <v-list class="background-ACE0E5 color-black">
                  <v-list-item
                     v-for="item in userProdileDropdown"
                     :key="item.title"
                     >
                     <v-list-item-title class="color-black">{{ item.title }}</v-list-item-title>
                  </v-list-item>
               </v-list>
            </v-menu>
            <!-- This menu bar is to display  the title only for sm and xs screens 
               class="hidden-md-and-up" helps us to hide for all screens md and larger than md. -->
            <v-menu class="ma-0 pa-0 background-ACE0E5">
               <template v-slot:activator="{ on, attrs }">
                  <v-btn class="hidden-md-and-up ma-0 pa-0" 
                     icon
                     v-bind="attrs"
                     v-on="on"
                     >
                     <v-icon color="#00A4B4" >mdi-dots-vertical</v-icon>
                  </v-btn>
               </template>
               <!-- The user account details which were hidden for sm and small screens are being populated here for those screens only. -->
               <v-menu class="background-ACE0E5">
                  <template v-slot:activator="{ on, dropdownMenu }">
                     <v-btn class="background-ACE0E5 color-black removeBoxShadow" style="width: 100%; text-align:left"                     
                        v-bind="dropdownMenu"
                        v-on="on"
                        >
                        Hi ABC 
                        <v-icon class="pa-0" color="#00A4B4">mdi-menu-down</v-icon>
                     </v-btn>
                  </template>
                  <v-list class="background-ACE0E5 color-black">
                     <v-list-item
                        v-for="item in userProdileDropdown"
                        :key="item.title"
                        >
                        <v-list-item-title class="color-black">{{ item.title }}</v-list-item-title>
                     </v-list-item>
                  </v-list>
               </v-menu>
               <v-list class="background-ACE0E5 color-black">
                  <v-list-item
                     v-for="item in menu"
                     :key="item.title"
                     >
                     <v-list-item-title class="color-black">{{ item.title }}</v-list-item-title>
                  </v-list-item>
               </v-list>
            </v-menu>
         </v-toolbar>
         <!-- Search box which is to be displayed only in case of sm and xs screens. -->
         <v-card class="hidden-sm-and-up removeBoxShadow br-0" style="background:white;color:#00A4B4; display: inherit;">
            <input type="text" color="black" class="pa-0 pl-4" style="width:85%; outline:none" placeholder="Explore The Beyond"></input>
            <!-- This is the search icon. -->
            <v-icon class="ma-2" color="#00A4B4">mdi-magnify</v-icon>
         </v-card>
      </v-card>
      <!-- This menu bar is to display  the title only for md and above screens.
         class="hidden-sm-and-down" hides it for all sm and smaller screens. 
         The code to display menu bar on sm screen is already added above. -->
      <v-card tile class="hidden-sm-and-down br-0">
         <v-toolbar dense color="#00A4B4">
            <v-toolbar-items>
               <v-btn class="removeBoxShadow" style="font-size:12px" color="#00A4B4"
                  v-for="item in menu"
                  :key="item.title"
                  >{{ item.title }}</v-btn>
            </v-toolbar-items>
         </v-toolbar>
      </v-card>
      <v-card class="pa-2 br-0" style="background:#D3EAEC; height:100%;">
         <CouponPopup/>
         <Product/>
      </v-card>
   </v-app>
</template>
<!-- This is the script to include title list in header.. 
   This can then be rendered / displayed using a loop and thus making an object like this makes it easy to display details. -->
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
       ],
      userProdileDropdown: [
         { title: 'My Orders' },
         { title: 'My Returns' },
         { title: 'My Profile' },
         { title: 'My Chat' },
         { title: 'My Feedback' },
         { title: 'My Cluesbucks' },
         { title: 'Help and Support' },
         { title: 'Sign Out' } 
       ],
     }),
   }
</script>
<!-- Script tag contains the definitions od user defined styling -->
<style>
   .background-ACE0E5{
   background : #ACE0E5 !important
   }
   .color-black{
   color : black !important
   }
   .cursorPointer {
   cursor : pointer;
   }
   .removeBoxShadow{
   box-shadow: 0 0 !important
   }
   .br-0{
   border-radius: 0px !important
   }
</style>
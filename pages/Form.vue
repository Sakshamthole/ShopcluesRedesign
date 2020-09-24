<template>

  <v-container>
  My Cart (2 Items)
  <v-row justify="left">
   
  
    <v-dialog v-model="dialog" max-width="760px"> <!-- stays even when clicked outside the window-->
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          dark
          v-bind="attrs"
          v-on="on"
        >
          2 offers applicable on this order
        </v-btn>
      </template>
     
      <v-card>
        <v-card-title>
        
          <span class="headline">Available Coupons</span>
           </v-card-title>
         
          
          
          
           <radio/>
           </v-card
           > <v-card-actions>
          <v-spacer></v-spacer>
          
          <v-btn color="blue darken-1" text @click="dialog = false">Save</v-btn>
          
        </v-card-actions>


       
        
      </v-card>
    </v-dialog>
  </v-row>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      dialog: false, //form appears after clicking on the activator "open dialog"-->
    }),
  }
</script>
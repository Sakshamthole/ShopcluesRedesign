<!-- These are the list of available offers. -->
<template>
   <v-container fluid>
      <!--<p>{{ radios || 'null' }}</p>-->
      <v-radio-group v-model="radios" :mandatory="false">
         <v-radio label="PREPAID40 You Save Rs 40." value="radio-1"></v-radio>
         <h5> Congrats! You are eligible for Flat Rs 40 off on Prepaid orders with minimum cart value of Rs 399 and Maximum discount of Rs 40. Use coupon code PREPAID40.</h5>
         <v-radio label="B2G75 You Save Rs. 75." value="radio-2"></v-radio>
         <h5>Congrats! You are eligible for Flat Rs 75 off on Prepaid and COD orders with minimum cart value of Rs 329. Use coupon code B2G75.</h5>
      </v-radio-group>
   </v-container>
</template>
<script>
   export default {
     data () {
       return {
         radios: 'radio-1',
       }
     },
   }
</script>
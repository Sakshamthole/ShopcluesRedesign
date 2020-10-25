<!-- These are the list of available offers. -->
<template>
   <v-container>
      <v-radio-group v-model="radios" :mandatory="false" style="color:black" color="black">
         <v-radio color="black" label="PREPAID40 You Save Rs 40." value="radio-1" light class="black--text"></v-radio>
         <p> Congrats! You are eligible for Flat Rs 40 off on Prepaid orders with minimum cart value of Rs 399 and Maximum discount of Rs 40. Use coupon code PREPAID40.</p>
         <v-radio color="black" label="B2G75 You Save Rs. 75." value="radio-2" light class="black--text"></v-radio>
         <p> Congrats! You are eligible for Flat Rs 75 off on Prepaid and COD orders with minimum cart value of Rs 329. Use coupon code B2G75.</p>
      </v-radio-group>
   </v-container>
</template>
<style scoped>
   .black--text /deep/ label {
   color: black;
   }
</style>
<script>
   export default {
     data () {
       return {
         radios: 'radio-1',
       }
     },
   }
</script>
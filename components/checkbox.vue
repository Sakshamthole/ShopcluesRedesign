<template>
  <v-container fluid>
    <p>{{ selected  }}</p>
    <v-checkbox v-model="selected" label="PREPAID40        You Save Rs. 40." value="John"></v-checkbox>
    <v-checkbox v-model="selected" label="FIRSTORDER You Save Rs. 30." value="Jacob"></v-checkbox>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
       selected: ['John']
       
      }
    },
  }
</script>
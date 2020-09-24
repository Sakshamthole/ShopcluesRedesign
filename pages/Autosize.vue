<template>
  <v-container class="grey lighten-5">
    <v-row
      v-for="n in 6"
      :key="n"
      :class="n === 6 ? 'mb-6' : ''"
      no-gutters
    >
      <v-col
        v-for="k in n "
        :key="k"
      >
        <v-card
          class="pa-2"
          outlined
          tile
        >
          {{ k }} of {{ n }}
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
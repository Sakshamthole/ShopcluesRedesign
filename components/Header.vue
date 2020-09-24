 <template>
 <v-app id="header" background="black">
      <v-card flat tile>
    <v-toolbar dense color="cyan">
      <v-toolbar-title>Title</v-toolbar-title>
       <v-spacer></v-spacer>
      <v-card style="background:white; display: inherit;width: 50% ;height:80%">
      <v-text-field color="cyan" ></v-text-field>
      <v-btn icon color="cyan">
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      </v-card>
      <v-spacer></v-spacer>
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
        </v-app>
    </v-toolbar>
  </v-card>

    <v-card flat tile>
    <v-toolbar dense color="blue">
       <v-spacer></v-spacer>
      <v-toolbar-items>
         <v-btn color="blue"
          v-for="item in menu"
          :key="item.icon"
          :to="item.link"
          flat
        >{{ item.title }}</v-btn>
      </v-toolbar-items>
    </v-toolbar>
  </v-card>
  </template>
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
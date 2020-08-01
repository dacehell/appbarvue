<template>
    <v-app>
        
  <v-card
    flat
    tile
    
  >
    <v-toolbar dense color="primary">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Appbar</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-toolbar>
  </v-card>
    <v-card>
    <v-navigation-drawer app v-model="drawer"
      absolute
      temporary
      left
    >
      <template v-slot:prepend>
        <v-list-item two-line>
          <v-list-item-avatar>
            <img src="https://randomuser.me/api/portraits/women/80.jpg">
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>Jane Smith</v-list-item-title>
            <v-list-item-subtitle>Logged In</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
            v-for="item in items"
            :key="item.title"
            :to="item.route"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-card>
    </v-app>
</template>

<script>
export default {
  name:'AppBar',
  data() {
      return {
          drawer: false,
          items: [
          { title: 'Home', icon: 'mdi-home-city', route:'/home'},
          { title: 'My Account', icon: 'mdi-account', route:'/about' },
          { title: 'Users', icon: 'mdi-account-group-outline', route:'/user' },
        ],
        
      }
  },
 

}
</script>
<style scoped>
    div.v-application--wrap:last-child{
        min-height:auto;
    }
</style>
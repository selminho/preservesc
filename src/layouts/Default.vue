<template>
  <v-app>
    <v-app-bar app color="black" dark elevation="1">
      <v-app-bar-nav-icon @click.stop="sidebar = !sidebar"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-icon>mdi-shark-fin </v-icon>
    </v-app-bar>
    <v-navigation-drawer app v-model="sidebar" :mini-variant.sync="mini">
      <v-list dense color="blue" dark>
        <v-list-item>
          <v-list-item-action>
            <v-icon @click.stop="sidebar = !sidebar">mdi-chevron-left</v-icon>
          </v-list-item-action>
        <v-list-item-title>
          <h3>blablabal</h3>
        </v-list-item-title>
        </v-list-item>
      </v-list>
      <v-list-item class="px=2" @click="mini = !mini">
        <v-list-item-avatar>
          <v-icon>mdi-jellyfish</v-icon>
        </v-list-item-avatar>
        <v-list-item-contend>Henry</v-list-item-contend>
        <v-btn icon small><v-icon>mdi-chevron-left</v-icon></v-btn>
      </v-list-item>
      <v-divider></v-divider>
      <v-list>
        <v-list-item v-for="item of items" :key="item.title" link :to="item.to">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-contet>{{ item.title }}</v-list-item-contet>
        </v-list-item>
      </v-list>
      
      
    </v-navigation-drawer>
    
    <v-main>
      <router-view></router-view>
    </v-main>
    <v-footer app class="py-3"
      ><span class="overline">Selminho &copy;2022</span></v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      sidebar: true,
      mini: false,
      items: [
        { title: "Home", icon: "mdi-beach" ,to: "/" },
        { title: "Perfil", icon: "mdi-account.cog" ,to: "/perfil" },
        { title: "Sair", icon: "mdi-exit-to-app" ,to: "/login" },
        
 
      ],
    };
  },
}
</script>

<style>
</style>
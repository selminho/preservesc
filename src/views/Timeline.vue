<template>
  <v-app>
    <v-app-bar app color="black" dark elevation="1">
      <v-app-bar-nav-icon @click.stop="sidebar = !sidebar"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-icon>mdi-shark-fin </v-icon>
    </v-app-bar>
    <v-navigation-drawer app v-model="sidebar">
      <v-list dense color="black" dark>
        <v-list-item>
          <v-list-item-action>
            <v-icon @click.stop="sidebar = !sidebar">mdi-chevron-left</v-icon>
          </v-list-item-action>
        <v-list-item-title>
          <h3><font face="FreeMono, monospace">menu</font></h3>
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
      <div>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width="1024"
      img-height="480"
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <!-- Text slides with image -->
      <b-carousel-slide
        caption="First slide"
        text="Nulla vitae elit libero, a pharetra augue mollis interdum."
        img-src="https://picsum.photos/1024/480/?image=52"
      ></b-carousel-slide>

      <!-- Slides with custom text -->
      <b-carousel-slide img-src="https://picsum.photos/1024/480/?image=54">
        <h1>Hello world!</h1>
      </b-carousel-slide>

      <!-- Slides with image only -->
      <b-carousel-slide img-src="https://picsum.photos/1024/480/?image=58"></b-carousel-slide>

      <!-- Slides with img slot -->
      <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
      <b-carousel-slide>
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="https://picsum.photos/1024/480/?image=55"
            alt="image slot"
          >
        </template>
      </b-carousel-slide>

      <!-- Slide with blank fluid image to maintain slide aspect ratio -->
      <b-carousel-slide caption="Blank Image" img-blank img-alt="Blank image">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse eros felis, tincidunt
          a tincidunt eget, convallis vel est. Ut pellentesque ut lacus vel interdum.
        </p>
      </b-carousel-slide>
    </b-carousel>

    <p class="mt-4">
      Slide #: {{ slide }}<br>
      Sliding: {{ sliding }}
    </p>
  </div>
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
<template>
<v-app>
    <div>
      <b-navbar class="black" toggleable="lg" type="dark" variant="info">
        <b-button squared variant="light" v-b-toggle.sidebar-1>
          <v-icon>mdi-shark-fin</v-icon>
        </b-button>
    <b-sidebar id="sidebar-1" title="MENU" shadow>
      <div class="black px-3 py-2">
         <v-list dense color="black" dark>
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
      </div>
    </b-sidebar>


        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="#" to="/login2">
            <font face="FreeMono, monospace">
              LOGIN ou CADASTRE-SE
              </font>
            </b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-form>
            </b-nav-form>
<b-navbar-brand href="#"><font face="FreeMono, monospace">PRESERVE</font></b-navbar-brand>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    
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
      <!-- slide 1 -->
      <b-carousel-slide>
          <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="@/assets/images/bravafloripa.png"
            alt="image slot"
          >
        </template>
        <h1 class="black">PRESERVE</h1>
        <h3 class="black">COM RESPEITO</h3>
      </b-carousel-slide>

      <!-- slide 2 -->
      <b-carousel-slide>
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="@/assets/images/whaletrash.png"
            alt="image slot"
          >
        </template>
        <h1 class="black">RESISTÊNCIA</h1>
      </b-carousel-slide>

      <!-- Slide 3 -->
      <b-carousel-slide>
      <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="@/assets/images/criança.png"
            alt="image slot"
          >
        </template>
        <h1 class="black">RECOMEÇO</h1>
      </b-carousel-slide>

      <!-- Slide 4 -->
      <b-carousel-slide>
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="@/assets/images/limpezadepraia.png"
            alt="image slot"
          >
        </template>
        <h1 class="black">REPENSAR</h1>
      </b-carousel-slide>

      <!-- Slide 5 -->
      <b-carousel-slide>
                <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="@/assets/images/logo2.png"
            alt="image slot"
          >
        </template>
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
    data() {
      return {
        novaTarefa: "",
        tarefas: [
          {titulo: "Tarefa 1"},
          {titulo: "Tarefa 2"},
          {titulo: "Tarefa 3"},
        ]
      };
    },
    methods: {
      adicionar(e) {
        e.preventDefault();
        this.tarefas.push({ titulo: this.novatarefa });
        this.novatarefa = "";  
      },
    }
  }
  </script>
  
  <style>
  
  </style>
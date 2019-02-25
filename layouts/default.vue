<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" fixed app>
      <v-list>
        <v-list-tile v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
  
    <v-toolbar fixed app>
      <v-toolbar-side-icon @click="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
    </v-toolbar>
    <v-content>
      <v-container>
        <v-layout column justify-center align-center>
          <v-flex xs12 sm8 md6>
            <v-card class="px-2" style="max-width: 960px;">
              <v-card-text>
                <nuxt />
              </v-card-text>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  export default {
    data() {
      return {
        drawer: false,
        items: [
          {
            icon: 'home',
            title: 'Home',
            to: '/'
          },
          {
            icon: 'bubble_chart',
            title: 'Chips',
            to: '/chips'
          },
          {
            icon: 'maximize',
            title: 'Toolbar',
            to: '/toolbar'
          }
        ],
        title: 'Tyler Design System'
      }
    }
  }
</script>

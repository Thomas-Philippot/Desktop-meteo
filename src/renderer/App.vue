<template>
  <div id="app">
    <v-app dark>
      <v-navigation-drawer
        fixed
        v-model="drawer"
        app
        clipped
      >
        <v-list>
          <v-list-tile
            router
            :to="item.to"
            :key="i"
            v-for="(item, i) in items"
            exact
          >
            <v-list-tile-action>
              <v-icon v-html="item.icon"></v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title v-text="item.title"></v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
      <v-toolbar fixed app clipped-left>
        <v-toolbar-side-icon @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
        <v-btn
          icon
          @click="back"
        >
          <v-icon>chevron_left</v-icon>
        </v-btn>
        <v-spacer></v-spacer>
        <v-toolbar-title v-text="title"></v-toolbar-title>
        <v-spacer></v-spacer>
      </v-toolbar>
      <v-content>
        <v-container fluid fill-height>
          <v-slide-y-transition mode="out-in">
            <router-view></router-view>
          </v-slide-y-transition>
        </v-container>
      </v-content>
      <v-footer :fixed="fixed" app>
        <v-spacer></v-spacer>
        <span>&copy; 2017</span>
      </v-footer>
    </v-app>
  </div>
</template>

<script>
  export default {
    name: 'my-project',
    data: () => ({
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        { icon: 'fas fa-home', title: 'Welcome', to: '/' },
        { icon: 'fas fa-lightbulb', title: 'Inspire', to: '/inspire' },
        { icon: 'fas fa-leaf', title: 'RM', to: '/rm' }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'My awesome APP'
    }),
    methods: {
      back () {
        this.$router.go(-1)
      }
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Roboto:300,400,500,700|Material+Icons');
  @import url('https://use.fontawesome.com/releases/v5.0.13/css/all.css');
  /* Global CSS */

</style>

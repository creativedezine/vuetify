<template>
  <nav>
    <v-toolbar flat app>
      <v-toolbar-side-icon class="grey--text" @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-spacer></v-spacer>
      <v-btn flat color="grey">
        <span>Sign Out</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
    </v-toolbar>
    <v-navigation-drawer app floating dark v-model="drawer">
      <v-list>
          <v-list-tile>
            <v-list-tile-avatar color="black">
              <v-img
                src="https://www.kamaliakhaddi.com/images/website/logos/logo1-new.png"
                height=100%
              />
            </v-list-tile-avatar>
            <v-list-tile-title class="title text-uppercase white--text">
              <span class="font-weight-light">Kamalia</span>
              <span> Khaddi</span>
            </v-list-tile-title>
          </v-list-tile>
      </v-list>
        <v-divider></v-divider>
      <v-list>
        <v-list-tile v-for="link in links" :key="link.text" router :to=" link.route ">
          <v-list-tile-action>
            <v-icon class="white--text">{{ link.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title class="white--text">
              {{ link.text }}
            </v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      links: [
        { icon: 'home', text: 'Home', route: '/' },
        { icon: 'reorder', text: 'Orders', route: '/orders' },
        { icon: 'class', text: 'Products', route: '/products' },
        { icon: 'settings', text: 'Settings', route: '/setting' }
      ]
    }
  },
  created () {
    this.openDrawer()
  },
  methods: {
    openDrawer: function () {
      this.drawer = true
    }
  }

}
</script>

<style>

</style>

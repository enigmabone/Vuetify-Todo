<template>
  <nav>
    <v-toolbar app src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">
      <v-app-bar-nav-icon class="grey--text" @click="popDrawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase">
        <router-link to="/" class="white--text">
          <span class="font-weight-light">Todo</span>
          <span class="font-weight-bold">List</span>
        </router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text dark color="white">
        <span>Sign Out</span>
        <v-icon right>mdi-exit-to-app</v-icon>
      </v-btn>
    </v-toolbar>
    <v-navigation-drawer v-model="drawer" app class="info">
      <v-list>
        <v-list-item-group v-for="link in links" :key="link.text">
          <router-link :to="link.route">
            <v-list-item>
              <v-icon class="white--text" left>{{ link.icon }}</v-icon>
              <v-list-item-content>
                <v-list-item-title class="white--text">{{ link.text}}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </router-link>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      drawer: false,
      links: [
        { icon: "mdi-view-dashboard", text: "Dashboard", route: "/" },
        { icon: "mdi-folder-image", text: "My Projects", route: "/projects" },
        { icon: "mdi-account-group", text: "Team", route: "/team" }
      ]
    };
  },
  methods: {
    popDrawer() {
      this.drawer = !this.drawer;
    }
  }
};
</script>

<style scoped lang="scss">
</style>
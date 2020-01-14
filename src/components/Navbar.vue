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

      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn depressed color="info" dark v-on="on">
            <v-icon left>mdi-chevron-down</v-icon>
            <span>Menu</span>
          </v-btn>
        </template>
        <v-list>
          <v-list-item v-for="link in links" :key="link.text">
            <router-link :to="link.route">
              <v-list-item-title class="primary--text">
                <v-icon class="primary--text" left>{{ link.icon }}</v-icon>
                {{ link.text }}
              </v-list-item-title>
            </router-link>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn text dark color="white">
        <span>Sign Out</span>
        <v-icon right>mdi-exit-to-app</v-icon>
      </v-btn>
    </v-toolbar>
    <v-navigation-drawer v-model="drawer" app class="info">
      <v-col align="center">
        <v-avatar size="100">
          <img src="/img/avatar-1.png" alt="user profile" />
        </v-avatar>
        <p class="white--text subheading mt-1">Blake Shelton</p>
      </v-col>
      <v-col align="center">
        <Popup />
      </v-col>
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
import Popup from "@/components/Popup.vue";
export default {
  name: "Navbar",
  components: {
    Popup
  },
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
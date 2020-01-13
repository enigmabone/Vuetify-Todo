<template>
  <div class="Dashboard">
    <h1 class="subheading grey--text">Dashboard Component</h1>
    <v-container class="my-5">
      <v-row class="mb-3">
        <v-tooltip top>
          <template v-slot:activator="{ on }">
            <v-btn small depressed color="grey lighten-4" @click="sortBy('title')" v-on="on">
              <v-icon small left>mdi-folder</v-icon>
              <span class="caption text-lowercase">By Project Name</span>
            </v-btn>
          </template>
          <span>Sort by project title</span>
        </v-tooltip>
        <v-tooltip top>
          <template v-slot:activator="{ on }">
            <v-btn small depressed color="grey lighten-4" @click="sortBy('person')" v-on="on">
              <v-icon small left>mdi-account-tie</v-icon>
              <span class="caption text-lowercase">By Name</span>
            </v-btn>
          </template>
          <span>Sort by person</span>
        </v-tooltip>
      </v-row>
      <v-card
        flat
        :class="`pa-3 mb-3 ${project.status}`"
        v-for="project in projects"
        :key="project.title"
      >
        <v-row wrap class="pa-2 project">
          <v-col xs="12" md="6">
            <div class="caption grey--text">Project Title</div>
            <div>{{ project.title }}</div>
          </v-col>
          <v-col xs="6" sm="4" md="2">
            <div class="caption grey--text">Person</div>
            <div>{{ project.person }}</div>
          </v-col>
          <v-col xs="6" sm="4" md="2">
            <div class="caption grey--text">Due Date</div>
            <div>{{ project.due }}</div>
          </v-col>
          <v-col xs="2" sm="4" md="2">
            <div>
              <v-chip small :class="`${project.status} white--text caption`">{{ project.status }}</v-chip>
            </div>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Dashboard",
  data() {
    return {
      projects: [
        {
          title: "Design a new website",
          person: "Dave Ramsey",
          due: "01/05/2020",
          status: "In-Progress"
        },
        {
          title: "Code up the homepage",
          person: "Kyle Miller",
          due: "01/20/2020",
          status: "In-Progress"
        },
        {
          title: "Design Video Component",
          person: "Steve Irwin",
          due: "02/07/2020",
          status: "Completed"
        },
        {
          title: "Design the Forum Component",
          person: "Blake Shelton",
          due: "02/22/2020",
          status: "New"
        }
      ]
    };
  },
  methods: {
    sortBy(prop) {
      this.projects.sort((a, b) => (a[prop] < b[prop] ? -1 : 1));
    }
  }
};
</script>
<style scoped lang="scss">
.New {
  border-left: 6px solid #30ad4b;
}
.Completed {
  border-left: 6px solid #b1b1b1;
}
.In-Progress {
  border-left: 6px solid #36ade9;
}
.v-chip.New {
  background: #30ad4b !important;
  border-left: none;
}
.v-chip.Completed {
  background: #b1b1b1 !important;
  border-left: none;
}
.v-chip.In-Progress {
  background: #36ade9 !important;
  border-left: none;
}
</style>
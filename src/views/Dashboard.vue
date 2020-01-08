<template>
  <div class="Dashboard">
    <h1 class="subheading grey--text">Dashboard Component</h1>
    <v-container class="my-5">
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
            <div class="caption grey--text">Status</div>
            <div>{{ project.status }}</div>
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
  }
};
</script>
<style scoped lang="scss">
.New {
  border-left: 6px solid #b1b1b1;
}
.Completed {
  border-left: 6px solid #10aa32;
}
.In-Progress {
  border-left: 6px solid #36ade9;
}
</style>
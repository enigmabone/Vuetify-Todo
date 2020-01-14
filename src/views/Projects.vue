<template>
  <div class="Projects">
    <h1 class="subheading grey--text">My Projects</h1>
    <v-container class="my-5">
      <v-expansion-panels>
        <v-expansion-panel v-for="project in myProjects" :key="project.title">
          <v-expansion-panel-header>{{ project.title }}</v-expansion-panel-header>
          <v-expansion-panel-content class="grey--text">
            <p>{{ project.person }}</p>
            <div class="font-weight-bold">Due By {{ project.due }}</div>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam sequi sapiente rerum quam fuga id alias cumque, neque quasi modi vel vero, fugit incidunt odit. Sunt sapiente enim totam porro.</p>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-container>
  </div>
</template>
<script>
export default {
  name: "Projects",
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
  computed: {
    myProjects() {
      return this.projects.filter(project => {
        return project.person === "Kyle Miller";
      });
    }
  }
};
</script>
<style scoped lang="scss">
</style>

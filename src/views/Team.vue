<template>
  <div class="Team">
    <h1 class="subheading grey--text">Team Component</h1>
    <v-container class="my-5">
      <v-row wrap>
        <v-col xs="12" sm="6" md="4" lg="3" v-for="person in team" :key="person.name">
          <v-card flat class="ma-3 pt-4 text-center">
            <v-avatar size="100">
              <img :src="`${person.avatar}`" alt="team member photo" />
            </v-avatar>
            <v-card-title class="justify-center">{{ person.name }}</v-card-title>

            <v-card-text class="text--primary text-center">{{ person.role }}</v-card-text>
            <v-card-actions class="justify-center">
              <v-btn depressed text color="grey">
                <v-icon small left>mdi-message-text-outline</v-icon>
                <span>Message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  name: "Team",
  data() {
    return {
      team: [
        {
          name: "Blake Shelton",
          role: "Country Music Star",
          avatar: "/img/avatar-1.png"
        },
        {
          name: "Dave Ramsey",
          role: "CEO, Ramsey Solutions",
          avatar: "/img/avatar-2.png"
        },
        {
          name: "Kyle Miller",
          role: "Front-End Developer",
          avatar: "/img/avatar-3.png"
        },
        {
          name: "Steve Irwin",
          role: "Animal Biologist",
          avatar: "/img/avatar-4.png"
        }
      ]
    };
  }
};
</script>
<style scoped lang="scss">
</style>
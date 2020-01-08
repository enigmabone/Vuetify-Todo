<template>
  <div class="Dashboard">
    <h1 class="subheading grey--text">Dashboard Component</h1>
    <v-container class="my-5">
      <v-row wrap>
        <v-col sm="12" md="6">
          <v-btn outlined block color="primary">Click Me</v-btn>
        </v-col>
        <v-col sm="12" md="6">
          <v-btn outlined block color="success">Click Me</v-btn>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Dashboard"
};
</script>
<style scoped lang="scss">
</style>
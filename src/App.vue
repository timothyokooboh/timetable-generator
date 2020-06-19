<template>
  <!-- Since Vuetify is installed, the entire content of the application must be wrapped inside the v-app compoenent. -->
  <v-app>
    <!-- Use the Navigation component so that it appears across all pages -->
    <Navigation />

    <!-- Since vuetify is installed, our routes will work by simply wrapping the router-view component inside the v-main component -->

    <v-main> 
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
import Navigation from "@/components/Navigation"
export default {
  name: 'App',

  components: {
   Navigation
  },

  data: () => ({
    //
  }),
};
</script>

<style>
  :root {
  --primary-color:#7c47ec;
  --secondary-color:#9767e7;
  --lavender: #e9dbf6;
  --blue-violet:#6b37d8;
  }

  .v-main__wrap {

      background-color: var(--lavender);
  }
</style>


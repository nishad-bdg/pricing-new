<template>
  <v-app style="background: #e5e5e5">
    <AppNavbar />
    <v-main> </v-main>
  </v-app>
</template>

<script>
import AppNavbar from "@/components/AppNavbar";
export default {
  name: "App",

  components: {
    AppNavbar,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans&display=swap");
</style> 
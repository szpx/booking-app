<template>
  <div>
    <v-app>
      <v-app-bar app outlined dark collapse-on-scroll>
        <v-app-bar-nav-icon
          color="blue"
          @click="drawer = true"
        ></v-app-bar-nav-icon>
        <v-app-bar-title>Booking App</v-app-bar-title>
        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
      </v-app-bar>
      <v-navigation-drawer v-model="drawer" app dark></v-navigation-drawer>
    </v-app>
    <div class="mt-32 bg-red-400"><span>Un peu de texte</span></div>
  </div>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    group: null,
  }),
}
</script>

<style></style>

<template>
  <v-app>
    <v-bottom-navigation v-model="value" :color="color" grow fixed>
      <v-btn v-for="(btn, i) in bottomNav" :key="i" :to="btn.to">
        <span>{{ btn.title }}</span>
        <v-icon>{{ btn.icon }}</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
export default {
  name: 'BottomNav',
  data() {
    return {
      bottomNav: [
        {
          to: '/',
          title: 'Accueil',
          icon: 'mdi-home',
        },
        {
          to: '/Reserver',
          title: 'Réserver',
          icon: 'mdi-calendar-search',
        },
        {
          to: '/Appeler',
          title: 'Appelez',
          icon: 'mdi-phone',
        },
        {
          to: '/Adresse',
          title: 'Adresse',
          icon: 'mdi-google-maps',
        },
      ],
      value: 'white',
    }
  },
  computed: {
    color() {
      switch (this.value) {
        case 0:
          return 'blue darken-1'
        case 1:
          return 'orange'
        case 2:
          return 'green'
        case 3:
          return 'red'
        default:
          return 'white'
      }
    },
  },
}
</script>
<style lang="postcss">
.v-item-group.v-bottom-navigation .v-btn {
  font-size: 0.6rem;
}
</style>

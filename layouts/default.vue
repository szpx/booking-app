<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app outlined hide-on-scroll>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-spacer />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-switch
        v-model="$vuetify.theme.dark"
        color="black"
        class="my-auto"
      ></v-switch>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-bottom-navigation v-model="value" :color="color" grow fixed>
      <v-btn>
        <span>Accueil</span>
        <v-icon>mdi-home</v-icon>
      </v-btn>
      <v-btn>
        <span>Réserver</span>
        <v-icon>mdi-calendar-search</v-icon>
      </v-btn>
      <v-btn>
        <span>Appeler</span>
        <v-icon>mdi-phone</v-icon>
      </v-btn>
      <v-btn>
        <span>Adresse</span>
        <v-icon>mdi-google-maps</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      value: null,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      title: 'Brand',
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
          return null
      }
    },
  },
}
</script>
<style lang="postcss">
.v-messages {
  display: none;
}
.v-item-group.v-bottom-navigation .v-btn {
  font-size: 0.6rem;
}
/* .v-icon.v-icon {
  font-size: 22px;
} */
</style>

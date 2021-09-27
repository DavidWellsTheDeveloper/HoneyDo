<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :clipped="clipped"
      temporary
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
    <v-app-bar
      :clipped-left="clipped"
      dark
      app
      color="primary" >
        <v-col cols="2">
          <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
        </v-col>
        <v-spacer />
          <v-toolbar-title v-text="title" />
          <v-img alt="Honey Do Logo" src="HoneyDoLogoImage.svg" min-width="250px" max-width="250px" style="margin: 20px;" />
        <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="true"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      clipped: true,
      collapseOnScroll: true,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Services',
          to: '/services'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'About',
          to: '/about'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Contact',
          to: '/contact'
        },
      ],
      title: 'Honey Do Cleaning'
    }
  }
}
</script>

<style>
  .v-toolbar__title {
    color: black;
    font-weight: bold;
    font-size: xx-large;
  }
</style>
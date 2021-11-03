<template>
  <v-app>
    <v-app-bar
      app
      color="green"
      dark
      elevation="0"
    >
      <div class="d-flex align-center">
        <h3>Front-end Roadmap Lars</h3>
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://www.larsvansusteren.nl"
        target="_blank"
        text
      >
        <span class="mr-2">larsvansusteren.nl</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <Roadmap/>
    </v-main>
  </v-app>
</template>

<script>
import Roadmap from './components/Roadmap';

export default {
  name: 'App',

  components: {
    Roadmap,
  },

  data: () => ({
    //
  }),
};
</script>

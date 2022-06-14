<template>
  <v-app>
    <router-link to="/"> Home</router-link>
    <router-link to="/about"> About</router-link>
    <router-view></router-view>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },

  data: () => ({
    //
  }),
};
</script>

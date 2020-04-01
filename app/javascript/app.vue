<template>
  <v-app id="app">
    <Header/>
    <router-view></router-view>
  </v-app>
</template>

<script>
import Vue from 'vue';
import VueRouter from 'vue-router';

import Header from "./components/Header";
import UserIndexPage from './components/user/UserIndexPage.vue';
import UserDetailPage from './components/user/UserDetailPage.vue';

const router = new VueRouter({
  routes: [
    { path: '/users/index',
      component: UserIndexPage  },
    { path: '/users/:id(\\d+)',  // :id は数値のみに制限する
      component: UserDetailPage  }
  ]
})

// ref. https://jp.vuejs.org/v2/guide/plugins.html#%E3%83%97%E3%83%A9%E3%82%B0%E3%82%A4%E3%83%B3%E3%81%AE%E4%BD%BF%E7%94%A8
Vue.use(VueRouter);

export default {
  router,
  components: {
    Header
  }
}
</script>

<style scoped>
</style>
<template>
  <dl>
    <dt>ID</dt>
    <dd>{{ user.id }}</dd>
    <dt>Email</dt>
    <dd>{{ user.email }}</dd>
    <router-link :to="{ name: 'UserIndexPage' }">一覧へ戻る</router-link>
  </dl>
</template>

<script>
import axios from 'axios';

export default {
  data: function () {
    return {
      user: {}
    }
  },
  mounted () {
    axios
      .get(`/api/v1/users/${this.$route.params.id}.json`)
      .then(response => (this.user = response.data))
  }
}
</script>

<style scoped>
</style>
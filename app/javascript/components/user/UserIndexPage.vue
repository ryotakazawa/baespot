<template>
    <table>
      <tbody>
        <tr>
          <th>ID</th>
          <th>email</th>
        </tr>
        <tr v-for="u in users" :key="u.id">
          <td><router-link :to="{ name: 'UserDetailPage', params: { id: u.id } }">{{ u.id }}</router-link></td>
          <td>{{ u.email }}</td>
        </tr>
      </tbody>
    </table>
</template>

<script>
import axios from 'axios';

export default {
  data: function () {
    return {
      users: []
    }
  },
  mounted () {
    axios
      .get('/api/v1/users.json')
      .then(response => (this.users = response.data))
  }
}
</script>

<style scoped>
p {
  font-size: 2em;
  text-align: center;
}
</style>
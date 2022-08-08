<template>
  <UserList :users="users" />
</template>

<script>
import UserList from "./components/UserList.vue";

import { loadUsers } from "./api.js";
export default {
  name: "App",
  components: {
    UserList,
  },
  data() {
    return { users: [], todos: [], hello: "world" };
  },

  mounted() {
    loadUsers().then((users) => {
      this.users = users;
    });
  },
};
</script>


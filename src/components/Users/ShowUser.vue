<template>
  <div>
    <h1>Server Side Programming</h1>
    <p>instructor: {{ user.instructor }}</p>
    <p>description: {{ user.name }} - {{ user.lastname }}</p>
    <p>email: {{ user.email }}</p>
    <p>password: {{ user.password }}</p>
  </div>
</template>
<script>
import UserService from "@/services/UserService";

export default {
  data() {
    return {
      user: null
    };
  },
  async created() {
    let userId = this.$route.params.userId;
    this.user = (await UserService.show(userId)).data
    console.log(this.userId)
  }
};
</script>
<style scoped></style>

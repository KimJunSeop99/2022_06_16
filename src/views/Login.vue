<template>

</template>

<script>
import User from '@/models/user'

export default {
  /* eslint-disable */
  name: "Login",
  data() {
    return{
      user: new User("",""),
      loading: false,
      message: ""
    }
  },
  computed: {
    loggedIn(){
      return this.$store.state.auth.status.loggedIn;
    }
  },
  created() {
    // 로그인이 되었으면 loggedIn = true
    // 로그인이 안되었으면 loggedIn = false
    // 로그인이 되었으면 사용자를 프로필 페이지로 안내
    if (this.loggedIn) {
      // 강제 profile 페이지로 강제 이동함
      this.$router.push("/profile");
    }
  },

  methods: {

  }

}
</script>

<style scoped>

</style>
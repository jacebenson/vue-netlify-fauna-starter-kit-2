<template>
  <main class="home space">
    <h1 style="text-align:center">Tskr.io</h1>
    <h2>Tasks made easy</h2>

    <div>
      <p>
        A task system that is mean't to keep tasks secure, simple and easy to
        customize
      </p>
    </div>
    <LoginSignup v-if="currentUser === null" />
    <div v-else id="greeting">
      <h2>🖐️ Welcome Back {{ currentUser.user_metadata.full_name }}!</h2>
      <p>
        You're logged in. Go check out your
        <router-link :to="{ name: 'journals' }">journals ➡️ </router-link>.
      </p>
    </div>
  </main>
</template>

<script>
import { mapGetters } from "vuex";
import LoginSignup from "../components/LoginSignup.vue";

export default {
  name: "Home",
  components: {
    LoginSignup
  },
  props: {
    msg: String
  },
  data() {
    return {};
  },
  computed: {
    ...mapGetters("auth", ["currentUser"])
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
#greeting {
  border-style: dashed;
  padding: 15px;
  border-radius: 15px;
  border-color: #c6c6c6;
  border-width: 1px;
  h2 {
    text-transform: capitalize;
  }
}
img#logo {
  //width: 100%;
  height: auto;
}
</style>

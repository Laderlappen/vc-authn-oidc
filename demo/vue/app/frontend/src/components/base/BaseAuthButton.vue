<template>
  <div v-if="keycloakReady">
    <v-btn v-if="authenticated" outlined @click="logout">
      <span>Logout</span>
    </v-btn>
    <v-btn v-else-if="hasLogin" outlined @click="login">
      <span>Login</span>
    </v-btn>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';

export default {
  name: 'BaseAuthButton',
  computed: {
    ...mapGetters('auth', [
      'authenticated',
      'createLoginUrl',
      'createLogoutUrl',
      'keycloakReady',
      'presReqConfId',
    ]),
    hasLogin() {
      return this.$route && this.$route.meta && this.$route.meta.hasLogin;
    },
  },
  methods: {
    login() {
      if (this.keycloakReady) {
        window.location.replace(
          this.createLoginUrl() + '&pres_req_conf_id=' + this.presReqConfId
        );
      }
    },
    logout() {
      if (this.keycloakReady) {
        window.location.replace(
          this.createLogoutUrl({
            redirectUri: `${location.origin}/${this.$config.basePath}`,
          })
        );
      }
    },
  },
};
</script>

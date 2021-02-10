<template>
  <div id="app">
    <HeaderBar :loginInfos="login_infos"/>
    <router-view :username="login_infos.username" @userLogged="logUser"/>
  </div>
</template>

<script>
import HeaderBar from '@/components/HeaderBar.vue';
import LoginPage from '@/views/LoginPage.vue';
    export default {
        components: {
          HeaderBar,
        },
        data() {
          return {
            login_infos: {
              is_logged: false,
              username: '',
            }
          }
        },
        methods: {
          logUser(payload) {
            this.login_infos.is_logged = true;
            this.login_infos.username = payload.username;
          }
        },
    }
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,600;0,700;0,800;1,800&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Lobster&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700;900&display=swap');
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
.router-link-exact-active {
  text-decoration: underline;
}
a {
  color: white;
  text-decoration: none;
}
input {
    width: 60%;
    margin: 0 auto 0 auto;
    font-size: 1.5em;
    padding: 15px 10px;
    border-radius: 15px;
    border: none;
    outline: none;
    &::placeholder {
        color: #A0A0A0;
    }
}
</style>
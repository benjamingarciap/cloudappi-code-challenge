<template>
  <v-app>
    <AppBar/>
    <v-main>
      <Hero :friends="friends" id="element"/>
      <UserList :friends="friends" :loading="loading" id="friend-list"/>
    </v-main>
    <Footer/>
  </v-app>
</template>

<script>
import AppBar from './components/AppBar';
import Hero from './components/Hero';
import UserList from './components/UserList';
import Footer from './components/Footer';

export default {
  name: 'App',

  components: {
    UserList,
    Hero, 
    AppBar,
    Footer
  },

  data: () => ({
    friends: null, 
    loading: true
  }),
  
  mounted: function() {
    fetch('https://my-user-manager.herokuapp.com/users', {
      method: 'get'
    })
    .then((response) => {
      return response.json()
    })
    .then((jsonData) => {
      this.loading = false;
      this.friends = jsonData
    })
  }
};
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600&display=swap');
</style>

<template>
  <v-app-bar
    app
    color="#FF8412"
    hide-on-scroll
  >
    <v-spacer/>
    <a
      class="app-bar-link"
      v-scroll-to="'#element'"
    >
      <v-icon
        x-large
        color="white"
      >
        {{ 'mdi-account-multiple' }}
      </v-icon>
    </a>
    <v-spacer/>
  </v-app-bar>
</template>

<script>

  export default {
    name: 'AppBar'
  }
  
</script>

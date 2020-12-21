<template>
  <v-card class="footer-wrapper">
    <v-footer
      v-bind="localAttrs"
      :padless="padless"
    >
      <v-card
        flat
        tile
        width="100%"
        class="lighten-1 text-center"
        color="#FF8412"
      >
        <v-card-text class="white--text">
            <v-hover
              open-delay="200"
            >
            <a 
              href="https://github.com/benjamingarciap" 
              target="blank" 
              class="text-decoration-none "
              
              >
              <v-icon 
                size="24px" 
                color="white"
                class="mx-4"
              >
                {{ 'mdi-github' }}
              </v-icon>
            </a>
             </v-hover>
          {{ new Date().getFullYear() }} — <strong>Benjamin Garcia</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      name: 'Footer',
      padless: true,
      variant: 'default'
    }),
  }
</script>

<style scoped lang="scss">
  .footer-wrapper{
    @media screen and (max-width: 320px) {
      max-width: 320px;
    }
  }

</style>

<template>
  <div>
    <div class="friend-list-container" v-if="loading === true">
        <v-progress-circular
          indeterminate
          color="#FF8412"
        ></v-progress-circular>
    </div>
    <div class="friend-list-container" v-if="!loading">
      <h1 class="friend-list-title">
        User List
      </h1>
      <div>
        <div
          v-for="(friend, i) in friends"
          :key="i"
        >
          <v-hover>
            <template v-slot:default="{ hover }">
              <v-card
                class="friend-card mx-2 mt-4"
                max-width="390"
              >
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-card-text>
                      <h1 class="headline mb-1">{{ friend.name }}</h1>
                      <p>{{ friend.email }}</p>
                    </v-card-text>
                  </v-list-item-content>
                  <v-list-item-avatar
                    tile
                    size="90"
                    color="white"
                  >
                    <v-icon 
                      x-large 
                      color="orange"
                    >
                      {{ 'mdi-account' }}
                    </v-icon>
                  </v-list-item-avatar>
                </v-list-item>
                <v-fade-transition>
                  <v-overlay
                    v-if="hover"
                    absolute
                    color="#00BCD4"
                  />
                </v-fade-transition>
              </v-card>
            </template>
          </v-hover>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  
  export default {
    name: 'UserList',
    props: {
      friends: Array, 
      loading: Boolean
    },
    data: () => ({
      show: false,
    })
  }

</script>

<style scoped lang="scss">

  .friend-list-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 90vh;

    @media screen and (max-width: 320px) {
      height: 110vh;
    }
  }

  .friend-list-title {
    width: 11.3em;
    font-family: 'Poppins', sans-serif;
    color: white;
    background-color: white; 
    font-size: 2.1em;
    letter-spacing: -1px;
    font-weight: 500;
    margin: 0;
    padding-left: 5px;
    opacity: 1;
    background-color: #FF8412;
    padding:0px 20px 0px 20px;
    animation-delay: 1.3s;
    text-align: center;
  }

</style>

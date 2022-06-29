<template>
  <v-container>
    <v-navigation-drawer
      v-model="drawer"
      :rail="rail"
      permanent
      location="right"
      @click="rail = false"
    >
      <v-list-item
        prepend-avatar="./assets/images/autronica_logo.png"
        title="John Leider"
      >
        <template v-slot:append>
          <v-btn
            variant="text"
            icon="mdi-chevron-left"
            @click.stop="rail = !rail"
          ></v-btn>
        </template>
      </v-list-item>

      <v-divider></v-divider>

      <v-list density="compact" nav>
        <v-list-item
          prepend-icon="mdi-home-city"
          title="Home"
          value="home"
        ></v-list-item>
        <v-list-item
          prepend-icon="mdi-account"
          title="My Account"
          value="account"
        ></v-list-item>
        <v-list-item
          prepend-icon="mdi-account-group-outline"
          title="Users"
          value="users"
        ></v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main style="height: 100vh">
      <v-img :src="require('./src/assets/boat.jpg')" />
    </v-main>
  </v-container>
</template>

<script lang="ts">
export default {
  data() {
    return {
      drawer: true,

      items: [
        { title: 'Home', icon: 'mdi-home-city' },
        { title: 'My Account', icon: 'mdi-account' },
        { title: 'Users', icon: 'mdi-account-group-outline' },
      ],
      rail: true,
    };
  },
};
</script>

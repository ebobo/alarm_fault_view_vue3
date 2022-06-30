<template>
  <v-card width="380" :theme="theme">
    <v-toolbar color="rgba(0,0,0,0)" flat>
      <v-toolbar-title>Side</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn rounded small @click="changeStatus()"> fold </v-btn>
      <v-btn rounded small @click="changeTheme()"> theme </v-btn>
    </v-toolbar>
    <v-banner
      lines="one"
      icon="mdi-lock"
      color="deep-purple-accent-4"
      class="my-4"
    >
      <v-banner-text> Banner with one line of text. </v-banner-text>

      <template v-slot:actions>
        <v-btn>Action</v-btn>
      </template>
    </v-banner>

    <v-banner
      lines="two"
      icon="mdi-weather-hurricane"
      color="error"
      class="my-4"
    >
      <v-banner-text>
        Banner with two lines of text. If the text is too long to fit on two
        lines then an ellipsis will be used to hide the remaining content. So
        this next line will be hidden.
      </v-banner-text>

      <template v-slot:actions>
        <v-btn>Action</v-btn>
      </template>
    </v-banner>

    <v-banner lines="three" icon="$warning" color="warning" class="my-4">
      <v-banner-text>
        Banner with three lines of text. One or two lines is preferable. Three
        lines should be considered the absolute maximum length on desktop in
        order to keep messages short and actionable.
      </v-banner-text>

      <template v-slot:actions>
        <v-btn>Action</v-btn>
      </template>
    </v-banner>
  </v-card>
</template>

<script lang="ts">
export default {
  data() {
    return {
      rail: false,
      theme: 'light',
    };
  },

  methods: {
    changeStatus() {
      this.rail = !this.rail;
    },

    changeTheme() {
      if (this.theme === 'dark') {
        this.theme = 'light';
      } else {
        this.theme = 'dark';
      }
    },
  },
};
</script>

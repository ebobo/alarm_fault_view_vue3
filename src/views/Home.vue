<template>
  <v-app>
    <v-row>
      <v-container>
        <v-btn class="ml-10" height="40" width="200" @click="openClose()">
          Close
          <v-icon>mdi-file-document-edit-outline</v-icon>
        </v-btn></v-container
      >

      <v-expand-x-transition>
        <side-card v-if="sidebarOpen" />
      </v-expand-x-transition>
      <v-expand-x-transition>
        <small-side-bar v-if="smallSideBarOpen" />
      </v-expand-x-transition>
    </v-row>
  </v-app>
</template>

<script lang="ts">
import SideCard from '../components/SideCard.vue';
// import SideBar from '../components/SideBar.vue';
import SmallSideBar from '../components/SmallSideBar.vue';

export default {
  components: {
    // SideBar,
    SideCard,
    SmallSideBar,
  },
  data(): {
    sidebarOpen: boolean;
    smallSideBarOpen: boolean;
  } {
    return {
      sidebarOpen: true,
      smallSideBarOpen: false,
    };
  },

  methods: {
    openClose() {
      if (this.sidebarOpen) {
        this.sidebarOpen = false;
        setTimeout(() => (this.smallSideBarOpen = true), 250);
      } else {
        this.smallSideBarOpen = false;
        setTimeout(() => (this.sidebarOpen = true), 50);
      }
    },
  },
};
</script>

<style scoped>
.fade-enter-from {
  opacity: 0;
}
.fade-enter-to {
  opacity: 1;
}

.fade-enter-active {
  transition: all 2s ease;
}

.fade-leave-from {
  opacity: 1;
}
.fade-leave-to {
  opacity: 0;
}

.fade-leave-active {
  transition: all 2s ease;
}
</style>
>

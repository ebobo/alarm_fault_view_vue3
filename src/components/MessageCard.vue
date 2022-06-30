<template>
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
</template>

<script lang="ts">
export default {
  props: {
    unit_id: {
      required: true,
      type: String,
      default: '',
    },
    unit_name: {
      required: true,
      type: String,
      default: 'unknow',
    },
    selected: {
      required: true,
      type: Boolean,
      default: false,
    },
    editable: {
      required: false,
      type: Boolean,
      default: true,
    },
    number_stroey: {
      required: true,
      type: Number,
      default: 0,
    },
  },
};
</script>

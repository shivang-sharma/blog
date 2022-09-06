<template>
  <v-btn icon>
    <v-icon v-if="bookmarkStatus == false" :large="large" color="#3b5998" @click="bookmarkStatus = !bookmarkStatus" >mdi-bookmark-outline</v-icon>
    <v-icon v-if="bookmarkStatus" :large="large" color="#3b5998" @click="bookmarkStatus = !bookmarkStatus">mdi-bookmark-check</v-icon>
  </v-btn>
</template>

<script>
export default {
  data() {
    return {
      nuxt: true,
      bookmarkStatus: false,
    };
  },
  props: {
    large: false
  },
  methods: {}
};
</script>
<style scoped></style>

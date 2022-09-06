<template>
  <v-btn icon>
    <v-icon v-if="likeStatus == false" color="#F44336" @click="likeStatus = !likeStatus">mdi-heart-outline</v-icon>
    <v-icon v-if="likeStatus" color="#F44336" @click="likeStatus = !likeStatus">mdi-heart</v-icon>
  </v-btn>
</template>

<script>
export default {
  data() {
    return {
      nuxt: true,
      likeStatus: false
    };
  },
  props: {
    slug: ""
  },
  methods: {}
};
</script>
<style scoped></style>

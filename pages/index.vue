/* eslint-disable */
<template>
  <v-container fluid>
    <v-row align="start" justify="start">
      <v-col
        v-for="card in cards"
        :key="card.title"
        cols="12"
        sm="6"
        md="4"
        lg="3"
      >
        <v-card max-width="370">
          <v-list-item>
            <v-list-item-avatar color="grey" />
            <v-list-item-content>
              <div class="headline">
                <h4>{{ card.title }}</h4>
              </div>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>

          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="194"
          />

          <v-card-text>
            Visit ten places on our planet that are undergoing the biggest
            changes today.
          </v-card-text>
          <v-card-subtitle class="pb-0">
            Dec 20,2019<span class="ml-8">-20 min read</span>
          </v-card-subtitle>
          <v-card-actions>
            <v-btn
              :to="{ name: 'posts-slug', params: { slug: card.title } }"
              text
              small
              color="deep-purple accent-4"
              :nuxt="nuxt"
            >
              Read
            </v-btn>
            <v-btn text small color="deep-purple accent-4">
              Bookmark
            </v-btn>
            <v-spacer />
            <span class="font-weight-light">29</span>
            <Like />
            <span class="font-weight-light">40</span>
            <Share />
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
<style scoped>
.headline {
  font-size: 2px;
}
</style>
<script>
// `/posts/${card.title}`
import Like from '../components/Like';
import Share  from '../components/Share'
export default {
  components: {
    Like,
    Share
  },
  data() {
    return {
      nuxt: true,
      cards: this.$store.state.posts.all
    };
  }
};
</script>

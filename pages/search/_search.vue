/* eslint-disable */
<template>
  <v-container fluid>
    <v-tabs>
      <v-tab active-class="tab" light>
        {{ search }}
      </v-tab>
      <v-tab-item>
        <v-row
          align="start"
          justify="start"
        >
          <v-col
            v-for="card in cards"
            :key="card.title"
            cols="12"
            sm="6"
            md="4"
            lg="3"
          >
            <v-card
              max-width="344"
            >
              <v-list-item>
                <v-list-item-avatar color="grey" />
                <v-list-item-content>
                  <v-list-item-title class="headline">
                    Our Changing Planet
                  </v-list-item-title>
                  <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
              <v-img
                src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
                height="194"
              />
              <v-card-text>
                Visit ten places on our planet that are undergoing the biggest changes today.
              </v-card-text>
              <v-card-subtitle class="pb-0">
                Dec 20,2019<span class="ml-8">-20 min read</span>
              </v-card-subtitle>
              <v-card-actions>
                <v-btn
                  :nuxt="nuxt"
                  :to="{name: 'posts-id', params: {id: card.title}}"
                  text
                  small
                  color="deep-purple accent-4"
                >
                  Read
                </v-btn>
                <v-btn
                  text
                  small
                  color="deep-purple accent-4"
                >
                  Bookmark
                </v-btn>
                <v-spacer />
                <span class="font-weight-light">29</span>
                <v-btn icon>
                  <v-icon color="#F44336">
                    mdi-heart
                  </v-icon>
                </v-btn>
                <span class="font-weight-light">40</span>
                <v-btn icon>
                  <v-icon>mdi-share-variant</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-tab-item>
    </v-tabs>
  </v-container>
</template>
<style scoped>
</style>
<script>
// `/posts/${card.title}`
export default {
  data () {
    return {
      search: this.$route.params.search,
      dense: false,
      nuxt: true
    }
  },
  computed: {
    cards () {
      return this.$store.state.posts.all.filter(post => (post.tags.includes(this.search) === true || post.title.includes(this.search) === true))
    }

  }
}
</script>

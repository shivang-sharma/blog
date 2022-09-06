/* eslint-disable */
<template>
  <v-app>
    <v-app-bar
      app
      :fixed="true"
      color="white"
      :elevate-on-scroll="true"
    >
      <v-toolbar-title>Title</v-toolbar-title>
      <v-spacer></v-spacer>
      <SearchBox />
      <!--       
      <v-text-field
        ref="query"
        v-model="query"
        @click:append="search()"
        placeholder="Search ..."
        append-icon="mdi-magnify"
        hide-details
        single-line
        rounded
      /> -->
    </v-app-bar>
    <!-- <v-app-bar
      fixed
      app
    >
      <v-row>
        <v-col
          cols="5"
          class="mt-1"
        >
          <nuxt-link :to="`/`" class="link">
            <h1>BLOGGGG</h1>
          </nuxt-link>
        </v-col>
        <v-spacer />
        <v-col
          cols="7"
          lg="6"
          class="pl-lg-12 ml-lg-12"
        >
          <v-row>
            <v-col
              lg="4"
            >
              <v-text-field
                ref="query"
                v-model="query"
                @click:append="search()"
                placeholder="Search ..."
                append-icon="mdi-magnify"
                hide-details
                single-line
                rounded
              />
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-app-bar> -->
    <v-main>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>
<style scoped>
.link{
  text-decoration: none;
}
</style>
<script>
import SearchBox from '../components/SearchBox'
export default {
  components: {
    SearchBox
  },
  data () {
    return {
      clipped: false,
      fixed: false,
      fluid: false,
    }
  },
}
</script>

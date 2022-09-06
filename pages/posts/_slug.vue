/* eslint-disable */
<template>
  <v-content>
    <v-row align-content="center" justify="center">
      <v-col cols="12" sm="11" md="9" lg="6" align-self="center">
        <div class="pl-lg-6 pb-lg-4">
          <h1 class="post-title ml-lg-0 ml-md-6 ml-sm-6 ml-1">
            {{ post.title }}
          </h1>
          <v-row  class="pl-md-7 pl-lg-0">
            <v-col cols="12" lg="7" md="7" sm="8" class="pb-0 mb-0">
              <v-row>
                <v-col cols="3" lg="2" md="2" sm="2" class="mr-lg-2 mr-md-0 ml-sm-6 ml-md-0 ml-3 avatar-custom">
                  <v-avatar
                    size="55px"
                  >
                    <img
                      alt="Avatar"
                      src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                    />
                  </v-avatar>
                </v-col>
                <v-col>
                  <v-row>
                    <h3>Shivang Sharma</h3>
                  </v-row>
                  <v-row>
                    <span class="date"
                      >Dec 25,2019<span class="ml-2">-2min read</span></span
                    >
                  </v-row>
                </v-col>
              </v-row>
            </v-col>
            <v-col cols="10" lg="4" md="4" sm="4" class="pl-6 pt-0 pt-md-8 pl-md-12 pt-sm-9 ml-6">
              <v-row>
                <SocialShare :slug="post.slug" />
                <Bookmark />
              </v-row>
            </v-col>
          </v-row>
        </div>
        <blockquote class="blockquote">
          {{ post.content }}
        </blockquote>
        <v-row>
          <v-col cols="12" lg="8" md="8" sm="8" class="pl-lg-8 pl-9 pt-0 pl-md-8 pl-sm-9">
            <v-btn
              v-for="tag in post.tags"
              :key="tag"
              :to="`/tag/${tag}`"
              elevation="true"
              class="mr-lg-1 mr-2 mt-2 tag"
              small
              color="light-pink"
              nuxt
            >
              {{ tag }}
            </v-btn>
          </v-col>
          <v-col>
            <v-row>
              <v-col class="pt-lg-0 pl-9 pt-md-0 pt-sm-0">
                <SocialShare :slug="post.slug" :large="true" />
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-divider class="mb-4 ml-lg-6 ml-md-6 ml-sm-5" />
      </v-col>
    </v-row>
    <v-row align-content="center" justify="center">
      <v-col cols="4" lg="1" md="1" sm="1" class="pt-lg-0 ml-lg-11 pt-sm-0 ml-sm-6 ml-md-12 pb-md-10 mr-2 mr-lg-0" align-self="center">
        <v-avatar size="65px" class="avatar-custom-profile">
          <img
            alt="Avatar"
            src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
          />
        </v-avatar>
      </v-col>
      <v-col cols="9" lg="3" md="6" sm="7" class="pt-0 mt-lg-0" align-self="center">
        <v-row>
          <p class="pl-12 mt-lg-0 ml-1 pl-lg-0 ml-lg-0 pl-md-4 ml-md-0 mt-md-2 mb-md-0 mt-sm-8 pl-sm-8 mb-sm-0 mb-0 written-by">WRITTEN BY</p>
        </v-row>
        <v-row class="pl-7 pl-lg-0 pl-md-4 pl-sm-9 user-name">
            <h3>Shivang Sharma</h3>
        </v-row>
        <v-row>
          <p class="user-description ml-lg-0 ml-md-4 ml-sm-9">
            Hey! I am a Software Engineer. Loves to OpenSource.
          </p>
        </v-row>
      </v-col>
      <v-col
        cols="6"
        lg="1"
        md="1"
        sm="1"
        class="mb-lg-12 pb-lg-6 mr-lg-8 mb-md-12 pb-md-6 mr-md-12 mr-sm-12 pb-sm-6 mb-sm-12 pr-sm-12 pt-0 follow-btn"
        align-self="center"
      >
        <v-btn elevation="0">Follow</v-btn>
      </v-col>
    </v-row>
    <v-row align-content="center" justify="center" class="ml-lg-8 mr-lg-8 ml-sm-12 mr-sm-8 divider-heading">
      <v-col cols="10" lg="11" md="12" sm="12" align-self="center">
        <h1 class="more-title">More Reads</h1>
        <v-divider />
      </v-col>
    </v-row>
    <v-row
      align-content="center"
      justify="center"
      class="ml-lg-12 mr-lg-12 pl-lg-12 pr-lg-12  ml-sm-1"
    >
      <v-col cols="9" lg="3" md="3" sm="5">
        <v-card :flat="flat" max-width="344">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="100"
          />
          <v-list-item>
            <v-list-item-content>
              <div class="headline">
                <nuxt-link :to="`/posts/test`" :nuxt="nuxt" class="link">
                  <h5>Our Changing Planet</h5>
                </nuxt-link>
              </div>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>
      <v-col cols="9" lg="3" md="3" sm="5">
        <v-card :flat="flat" max-width="344">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="100"
          />
          <v-list-item>
            <v-list-item-content>
              <div class="headline">
                <nuxt-link :to="`/posts/test`" :nuxt="nuxt" class="link">
                  <h5>Our Changing Planet</h5>
                </nuxt-link>
              </div>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>
      <v-col cols="9" lg="3" md="3" sm="5">
        <v-card :flat="flat" max-width="344">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="100"
          />
          <v-list-item>
            <v-list-item-content>
              <div class="headline">
                <nuxt-link :to="`/posts/test`" :nuxt="nuxt" class="link">
                  <h5>Our Changing Planet</h5>
                </nuxt-link>
              </div>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>
      <v-col cols="9" lg="3" md="3" sm="5">
        <v-card :flat="flat" max-width="344">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="100"
          />
          <v-list-item>
            <v-list-item-content>
              <div class="headline">
                <nuxt-link :to="`/posts/test`" :nuxt="nuxt" class="link">
                  <h5>Our Changing Planet</h5>
                </nuxt-link>
              </div>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>
      <v-col cols="9" lg="3" md="3" sm="5">
        <v-card :flat="flat" max-width="344">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="100"
          />
          <v-list-item>
            <v-list-item-content>
              <div class="headline">
                <nuxt-link :to="`/posts/test`" :nuxt="nuxt" class="link">
                  <h5>Our Changing Planet</h5>
                </nuxt-link>
              </div>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>
      <v-col cols="9" lg="3" md="3" sm="5">
        <v-card :flat="flat" max-width="344">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="100"
          />
          <v-list-item>
            <v-list-item-content>
              <div class="headline">
                <nuxt-link :to="`/posts/test`" :nuxt="nuxt" class="link">
                  <h5>Our Changing Planet</h5>
                </nuxt-link>
              </div>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>
      <v-col cols="9" lg="3" md="3" sm="5">
        <v-card :flat="flat" max-width="344">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="100"
          />
          <v-list-item>
            <v-list-item-content>
              <div class="headline">
                <nuxt-link :to="`/posts/test`" :nuxt="nuxt" class="link">
                  <h5>Our Changing Planet</h5>
                </nuxt-link>
              </div>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>
      <v-col cols="9" lg="3" md="3" sm="5">
        <v-card :flat="flat" max-width="344">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="100"
          />
          <v-list-item>
            <v-list-item-content>
              <div class="headline">
                <nuxt-link :to="`/posts/test`" :nuxt="nuxt" class="link">
                  <h5>Our Changing Planet</h5>
                </nuxt-link>
              </div>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>
    </v-row>
  </v-content>
</template>
<style scoped>
.headline {
  font-size: 2px;
}
.date {
  color: grey;
}
.social {
  margin-left: 600px;
}
.tag {
  color: grey;
}
.link {
  text-decoration: none;
  color: black;
}
.link :hover {
  cursor: pointer;
}
.user-description{
  display: block;
}
@media only screen and (max-width: 540px){
  .user-description{
    display: block;
    margin-top: -6px;
    margin-left: 38px;
  }
  .more-title{
    font-size: 22px;
  }
  .link {
    font-size: 20px;
    line-height: 1em;
  }
  .post-title{
    margin-left: 25px !important;
  }
  .avatar-custom{
    padding-left: 30px;
    margin-right: -38px;
  }
  .avatar-custom-profile{
    margin-left: -160px;
  }
  .written-by{
    margin-top: -75px;
    margin-left: -11px !important;
  }
  .user-name{
    margin-top: -55px;
    margin-left: -2px;
  }
  .follow-btn{
    margin-left: 530px;
    margin-top: -180px;
  }
  .divider-heading{
    margin-left: -50px;
    margin-right: -60px;
  } 
  .user-description{
    margin-left: 60px;
    display: none;
  }
  .follow-btn{
    margin-left: 480px;
    margin-top: -122px;
  }
  .divider-heading{
    margin-left: -35px;
    margin-right: -38px;
  }
}
@media only screen and (max-width:  418px){
  .avatar-custom{
    margin-right: 0px;
  }
  .avatar-custom-profile{
    margin-left: -110px;
  }
  .written-by{
    margin-top: -75px;
    margin-left: 11px !important;
  }
  .user-name{
    margin-top: -55px;
    margin-left: 20px;
  }
  .follow-btn{
    margin-left: 0px;
    margin-top: 0px;
  }
}
@media only screen and (max-width:  385px){
    .avatar-custom{
      margin-right: 10px;
    }
    .avatar-custom-profile{
      margin-left: -110px;
    }
    .written-by{
      margin-top: -75px;
      margin-left: 11px !important;
    }
    .user-name{
      margin-top: -55px;
      margin-left: 20px;
    }
    .follow-btn{
      margin-left: 0px;
      margin-top: 0px;
    }
}
@media only screen and (max-width:  325px){
  .avatar-custom{
    margin-left: -2px!important;
  }
  .avatar-custom-profile{
    margin-left: -92px;
  }
  .post-title{
    margin-left: 12px!important;
  }
}
@media only screen and (max-width:  360px){
  .avatar-custom-profile{
    margin-left: -95px;
  }
  .avatar-custom{
    margin-left: -2px!important;
  }
  .post-title{
    margin-left: 12px!important;
  }
}
@media only screen and (max-width:  280px){
  .user-description{
    display: none;
  }
  .more-title{
    font-size: 22px;
  }
  .link {
    font-size: 20px;
    line-height: 1em;
  }
}
</style>
<script>
import SocialShare from "../../components/social_share/SocialShare";
import Bookmark from "../../components/Bookmark"
export default {
  components: {
    SocialShare,
    Bookmark
  },
  data() {
    return {
      slug: this.$route.params.slug,
      posts: this.$store.state.posts.all,
      nuxt: true,
      flat: true
    };
  },
  computed: {
    post() {
      return this.$store.state.posts.all.find(post => post.title === this.slug);
    },
    related() {
      return this.$store.state.posts.all.filter(
        post => post.title !== this.slug
      );
    }
  }
};
</script>

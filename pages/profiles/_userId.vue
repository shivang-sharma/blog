<template>
<v-content>
  <v-row align-content="center" justify="center">
    <v-col
      cols="12"
      lg="1"
    >
      <img
        src="https://picsum.photos/id/11/500/300" 
        class="responsive-profile-image"
        alt=""
      />
    </v-col>
    <v-col
      cols="12"
      class="pt-0 pl-0 pr-0"
      lg="6"
      md="9"
      sm="11"
      align-self="center"
    >
      <v-row class="pl-8 pr-8">
        <v-col><p class="user-name">Shivang Sharma</p></v-col>
      </v-row>
      <v-row class="pl-3">
        <v-col><v-btn elevation="0">Follow</v-btn></v-col>
        <v-col><p class="follower-count" >32K Followers</p></v-col>
        <v-col><p class="about-link">About</p></v-col>
      </v-row>
      <v-divider />
      <div class="pl-4 pr-4">
        <v-row class="pl-6 pr-6">
          <v-row>
            <v-col>
              <p class="publish-date">22 hour ago</p>
            </v-col>
          </v-row>
          <v-row>
            <v-col class="pt-0 pb-0 post-title"><p>Dependency Confusion: How I Hacked Into Apple, Microsoft and Dozens of Other Companies</p></v-col>
          </v-row>
          <v-row>
            <v-col class="pt-0 post-sub-title"><p>The Story Of a Novel Supply Chain Attack</p></v-col>
          </v-row>
          <v-row>
            <v-col>
              <img src="https://miro.medium.com/max/1250/1*64Io23eVHdWD_WB_s7PTvQ.jpeg" alt="" class="post-image">
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <p class="content-overview">
                Ever since I started learning how to code, I have been fascinated by the level of trust we put in a simple command like this one:
  pip install package_name
  Some programming languages, like Python, come with an easy, more or less official method of installing dependencies for your projects. These installers are usually tied to public code repositories where anyone can freely upload code packages for others to use.
  You have probably heard of these tools already — Node has npm and the npm registry, Python’s pip uses PyPI (Python Package Index), and Ruby’s gems can be found on… well, RubyGems. …

              </p>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <a class="read-more" href="#">Read more-11 min read</a>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <Like />
            </v-col>
            <v-col>
              <Share />
            </v-col>
            <v-col>
              <Bookmark />
            </v-col>
          </v-row>
        </v-row>
        <v-divider />
      </div>
    </v-col>
  </v-row>
</v-content>
</template>
<style scoped>
@media only screen and (min-width:  280px){
  .user-name{
    font-size: 27px;
    line-height: 34px;
    letter-spacing: 0;
    font-weight: 700;
    font-family: sohne, "Helvetica Neue", Helvetica, Arial, sans-serif;
    word-break: break-word;
    color: rgba(25, 25, 25, 1);
  }
  .follower-count{
    line-height: 24px;
    color:  rgba(117, 117, 117, 1);
    font-family: sohne, "Helvetica Neue", Helvetica, Arial, sans-serif;
  }
  .about-link{
     font-family: sohne, "Helvetica Neue", Helvetica, Arial, sans-serif;
     color: rgba(117, 117, 117, 1);
  }
  .publish-date{
    color: rgba(117, 117, 117, 2);
    line-height: 20px;
    font-size: 14px;
    font-family: sohne, "Helvetica Neue", Helvetica, Arial, sans-serif;
    font-weight: bold;
  }
  .post-title{
    letter-spacing: 0;
    line-height: 28px;
    font-size: 22px;
    font-style: normal;
    color: rgba(41, 41, 41, 1);
    word-break: break-word;
    font-weight: 700;
  }
  .post-sub-title{
    font-style: normal;
    letter-spacing: 0;
    color: rgba(117, 117, 117, 1);
    font-weight: bold;
    word-break: break-word;
  }
  .content-overview{
    word-break: break-word;
    font-size: 18px;
    line-height: 28px;
    font-family: charter, Georgia, Cambria, "Times New Roman", Times, serif;
    color: rgba(41, 41, 41, 1);
    font-weight: 400;
  }
  .read-more{
    line-height: 20px;
    font-size: 14px;
    font-family: sohne, "Helvetica Neue", Helvetica, Arial, sans-serif;
    font-weight: 400;
    color: rgba(26, 137, 23, 1);
    text-decoration: none;
  }
  .post-image{
    width: 225px;
    height: 150px;
  }
  .responsive-profile-image{
    display: none;
  }
}
@media only screen and (min-width:  320px){
  .publish-date{
    line-height: 20px;
    font-size: 14px;
    font-weight: 400;
    margin-top: 30px;
    margin-bottom: -5px;
  }
  .post-sub-title{
    line-height: 24px;
    font-size: 18px;
    font-weight: 400;
  }
  .post-image{
    width: 265px;
    height: 180px;
  }
  .content-overview{
    letter-spacing: -0.003em;
    font-size: 18px;
    line-height: 28px;
    font-weight: 400;
  }
}
@media only screen and (min-width:  360px){
  .post-image{
    width: 300px;
    height: 200px;
  }
}
@media only screen and (min-width:  375px){
  .post-image{
    width: 320px;
    height: 230px;
  }
  .post-sub-title{
    line-height: 24px;
    font-size: 18px;
    font-weight: 400;
    margin-bottom: -25px;
  }
  .publish-date{
    line-height: 20px;
    font-size: 14px;
    font-weight: 400;
  }
  .follower-count{
    margin-top: 6px;
  }
  .about-link{
    margin-top: 6px;
  }
}
@media only screen and (min-width:  411px){
  .post-image{
    width: 350px;
    height: 250px;
  }
  .content-overview{
    word-break: break-word;
    letter-spacing: -0.003em;
    font-size: 18px;
    line-height: 28px;
    font-weight: 400;
  }
}
@media only screen and (min-width:  414px){
  .post-image{
    width: 350px;
    height: 250px;
  }
  .content-overview{
    letter-spacing: -0.003em;
    font-size: 18px;
    line-height: 28px;
    font-weight: 400; 
  }
  .publish-date{
    margin-top: 30px;
    margin-bottom: -5px;
  }
}
@media only screen and (min-width:  540px){
  .follower-count{
    margin-left: -60px;
    margin-top: 10px;
    margin-bottom: -10px;
  }
  .about-link{
    margin-left: -100px;
    margin-top: 10px;
    margin-bottom: -10px;
  }
  .publish-date{
    margin-top: 20px;
    margin-bottom: -2px;
  }
  .post-image{
    width: 480px;
    height: 300px;
  }
}
@media only screen and (min-width:  768px){
  .post-image{
    width: 650px;
    height: 380px;
  }
  .post-title{
    letter-spacing: -0.014em;
    line-height: 44px;
    font-size: 36px;
    font-style: normal;
    font-weight: 700;
  }
  .publish-date{
    line-height: 20px;
    font-size: 14px;
    font-weight: 400;
  }
  .post-sub-title{
    line-height: 28px;
    font-size: 22px;
    font-weight: 400;
  }
  .follower-count{
    margin-left: -100px;
  }
  .about-link{
    margin-left: -200px;
  }
  .content-overview{
    letter-spacing: -0.003em;
    line-height: 32px;
    font-size: 21px;
    font-weight: 400;
  }
}
@media only screen and (min-width:  1024px){
  .content-overview{
    letter-spacing: -0.003em;
    line-height: 32px;
    font-size: 21px;
    font-weight: 400;
  }
  .post-image{
    width: 700px;
    height: 450px;
  }
  .post-title{
    letter-spacing: -0.014em;
    line-height: 44px;
    font-size: 36px;
    font-weight: 700;
  }
  .publish-date{
    font-size: 18px;
  }
  .post-sub-title{
    line-height: 28px;
    font-size: 22px;
    font-weight: 400;
  }
}@media only screen and (min-width:  1054px){
  .responsive-profile-image{
    display: block;
    width: 150px;
    height: 150px;
    border-radius: 100%;
    position: -webkit-sticky;
    position: fixed;
    top: 10;
    margin-left: -50px;
  }
  .follower-count{
    margin-left: -130px;
  }
  .about-link{
    margin-left: -250px;
  }
  .user-name{
    font-size: 30px;
  }
}
</style>
<script>
import Share from '../../components/Share'
import Like from '../../components/Like'
import Bookmark from '../../components/Bookmark'
export default {
  components : {
    Share,
    Like,
    Bookmark
  }
};
</script>

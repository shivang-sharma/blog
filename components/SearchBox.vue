<template>
  <div class="searchBox">
    <input v-model="query" class="searchInput" type="text" name="search" placeholder="Search" v-on:input="input=true"/>
    <button class="searchButton" v-on:click="search">
      <v-icon>mdi-magnify</v-icon>
    </button>
  </div>
</template>
<style scoped>
.searchBox {
    position: absolute;
    top: -20%;
    left: 80%;
    transform:  translate(-50%,50%);
    background: whitesmoke !important;
    height: 45px;
    border-radius: 40px !important;
}
.searchBox:hover > .searchInput {
    width: 240px;
    padding-left: 20px;
}
.searchBox:hover > .searchButton {
  background: white;
  color : #2f3640;
  margin-top: 2px;
  margin-right: 2px;
  width: 40px;
  height: 40px;
}
.searchButton {
    border:none;
    background: whitesmoke;
    border: none;
    float: right;
    width: 45px;
    height: 45px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: 0.4s;
}
.searchInput {
    outline:none;
    border:none;
    background: none !important;
    float:left;
    color: black;
    font-size: 16px;
    transition: 0.4s;
    line-height: 40px;
    width: 0px;
}
@media screen and (max-width: 620px) {
  .searchBox{
    height: 40px;
    top: -23%;
    left: 65%;
  }
  .searchBox:hover > .searchButton{
    background: whitesmoke;
  }
}
</style>
<script>
export default {
  data () {
    return {
      input: false,
      query: null
    }
  },
  methods: {
    search () {
      if(this.input == true && this.query != null && this.query.length>0){
        this.$router.push({ path: `/search/${this.query}` })
        this.query = null
      }
    }
  }
}
</script>
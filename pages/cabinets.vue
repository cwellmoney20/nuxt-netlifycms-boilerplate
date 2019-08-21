<template lang="html">
  <div class="main">
    <div class="main-header">
      <h1>{{siteInfo.sitename}}</h1>
      <p>{{siteInfo.sitedescription}}</p>
    </div>
    <div class="posts-list">
      <h2 class="posts-list-title">cabinets</h2>
      <p class="post-link" v-for="post in cabinets" :key="post.path">
        <span>{{ post.title }}</span>
        <img :src="post.thumbnail" alt="Smiley face" height="42" width="42">
      </p>
    </div>
  </div>
</template>

<script>
export default {
    // async asyncData({ params, app, payload, route, store }) {
    //     let cabinets = await import(`~/content/cabinets${/\.md$/}`);
    //     console.log(cabinets)
    //     return {
    //         cabinets
    //     };
    // },
  computed: {
    cabinets() {
      return this.$store.state.cabinets;
    },
    siteInfo() {
      return this.$store.state.siteInfo;
    }
  }
}
</script>

<style lang="css" scoped>
.posts-list {
  width: 100%;
  background-color: whitesmoke;
  padding: 20px;
  margin-top: 35px;
}
.post-link {
  padding-top: 10px;
}
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}
.main-header {
  text-align: center;
}
</style>

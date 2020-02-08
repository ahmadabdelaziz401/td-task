<template>
  <section>
    <div class="title">
      <p>CNN.com - RSS Channel - App International Edition</p>
    </div>
    <div class="container">
      <template v-for="(card,index) in allCards">
        <Card :card="card" :key="index"/>
      </template>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
import Card from '../components/Card'
export default {
  name:'Home',
  data() {
    return {
      feed: {},
      allCards: [],
      card: '',
    };
  },
  components : {
    Card
  },
  methods:{
    fetchData(){
      axios.get("https://api.rss2json.com/v1/api.json?rss_url=http://rss.cnn.com/rss/edition.rss")
      .then(res => {
        if(res.data.status == 'ok')
        this.allCards = res.data.items;
        this.feed = res.data.feed;
      })
    }
  },
  created() {
    this.fetchData();
  }

}
</script>

<style>
body{
  font-family: Arial, sans-serif;
  background-color: black;
}
.container {
    display: flex;
    flex-wrap: wrap;
}
.title {
  padding-top: 5px;
  color: #484848;
  font-size: 23px;
}
</style>


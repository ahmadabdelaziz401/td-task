<template>
  <div class="container-box" :style="{'background-image': 'url('+card.enclosure.link+')'}">
    <h1>{{card.title}}</h1>
    <p>{{card.pubDate? card.pubDate.substring(0,10): '' }}</p>
  </div>
</template>

<script>
export default {
  name:'Card',
  props: ["card"]
}
</script>

<style scoped>
.container-box {
    background-size: cover;
    background-position: center;
    flex: 1 1 21%;
    margin: 2px;
    box-shadow: 0px 0px 100px 10px black inset;
}

.container-box h1 {
    max-width: 300px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    color: #ffffff;
    margin-top: 55%;
    margin-left: 1%;
    font-size: 23px;
}

.container-box p {
    color: #ffffff;
    margin-left: 1%;
    font-size: 12px;
} 
</style>


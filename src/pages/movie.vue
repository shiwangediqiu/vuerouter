<template>
  <div>
    <div class="head">
    <<span>热门电影排行榜top250</span>
    </div>
    <ul class="ul">
      <li class="li"><v-link href="/0-50">0-50</v-link></li>
      <li class="li"><v-link href="/51-100">51-100</v-link></li>
      <li class="li"><v-link href="/101-150">101-150</v-link></li>
      <li class="li"><v-link href="/151-200">151-200</v-link></li>
      <li class="li"><v-link href="/201-250">201-250</v-link></li>
    </ul>

    <slot></slot>
    </div>
</template>

<script>
  import VLink from '../components/VLink.vue'

  export default {
    components: {
      VLink
    }
  }
</script>

<style>
  .head {
    border: solid 1px white;
    height: auto;
    width: 100%;
    font-size: 4em;
    background-color: #e1e1e1;
    padding-top: 12px;
        }
  .head>span {
    border: solid 1px #e1e1e1;
    text-align: center;
    margin-left: 30%;
        }
  .nav {
    border-bottom: 1px solid #e1e1e1;
    height: 100px;
    font-size: 50px;
    display: flex;
    text-align: center;
    margin: auto;
    color: #b4b4b4;
        }
  .ul {
    border-bottom: 1px solid #e1e1e1;
    height: auto;
    width: 80%;
    font-size: 3em;
    display: flex;
    text-align: center;
    margin: auto;
    color: #b4b4b4;
    list-style: none;
    }
  .li {
    flex: 1;
    padding-top: 20px;
    list-style: none;
        }
  .li:hover {
    color: black;
    border-bottom: solid 3px black;
        }        
</style>

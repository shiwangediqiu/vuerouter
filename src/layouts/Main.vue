<template>
  <div>
    <ul class="ul">
      <li class="li"><v-link href="/movie">电影</v-link></li>
      <li class="li"><v-link href="/book">书籍</v-link></li>
      <li class="li"><v-link href="/television">电视</v-link></li>
      <li class="li"><v-link href="/music">音乐</v-link></li>
      <li class="li"><v-link href="/city">同城</v-link></li>
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

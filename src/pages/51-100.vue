<template>
  <main-layout>
    <div class="main"> 
      <ul>
        <li v-for="article in articles">
          {{article.title}}
        </li>
      </ul>
    </div>
  </main-layout>
</template>

<script>
  import MainLayout from '../layouts/Main.vue'

  export default {
    components: {
      MainLayout
    },

    data() {
    return {
      articles: []
      }
    },
  
    mounted: function() {
    this.$http.jsonp('https://api.douban.com/v2/movie/top250?count=50', {}, {
        headers: {
 
        },
        emulateJSON: true
    }).then(function(response) {
      // 这里是处理正确的回调
 
        this.articles = response.data.subjects
        // this.articles = response.data["subjects"] 也可以
 
    }, function(response) {
        // 这里是处理错误的回调
        console.log(response)
    });
  }

  }
</script>

<style>
    .main>ul {
    height: 100px;
    width: 80%;
    font-size: 20px;
    display: flex;
    text-align: center;
    margin: auto;
    color: #b4b4b4;
    list-style: none;
    }
    .main>li {
    flex: 1;
    padding-top: 20px;
    list-style: none;
    display: inline-block;
    }
    li:hover {
    color: black;
    border-bottom: solid 3px black;
    }
</style>

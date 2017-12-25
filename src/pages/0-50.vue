<template>
  <main-layout>
    <div class="main">
    <p>rank 0-50</p> 
      <ul>
        <li v-for="(article,index) in articles">
          <p>电影名：{{article.title}}</p>
          <p>上映时间：{{article.year}}</p>
          <p>分类：{{article.genres[0]}}、{{article.genres[1]}}</p>
          <p>评分：最高--{{article.rating.max}}，最低--{{article.rating.min}}，平均--{{article.rating.average}}</p>
          <p><img :src="article.images.medium"></p>
          <p><span v-for='article2 in articles.directors'>{{article2.name}}</span></p> 
        </li><br />
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
      articles: [],
      year: []
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
    .main {
      border: solid 1px red;
      height: auto;
      width: 40%;
      margin: auto;
      text-align: center;
    }
    .main>ul {
    height: auto;
    width: 80%;
    font-size: 20px;
    margin: auto;
    color: #b4b4b4;
    }
    .main>ul>li {
    padding-top: 0px;
    list-style: none;
    }
    li:hover {
    color: black;
    }
</style>

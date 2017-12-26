<template>
  <main-layout>
    <div class="main"> 
      <ul>
        <li v-for="(article,index) in articles">
          <h3>第{{index+1}}名</h3>
          <p>电影名：{{article.title}}</p>
          <p>上映时间：{{article.year}}  分类：{{article.genres[0]}}、{{article.genres[1]}}</p>
          <p><span>导演：</span><span v-for='article2 in article.directors'>{{article2.name}}</span></p>
          <p><span>主演：</span><span v-for="(article3,index) in article.casts">{{article3.name}}<span
              v-if='index < article.casts.length -1'>/</span></span></p>
          <p>评分：最高--{{article.rating.max}}，最低--{{article.rating.min}}，平均--{{article.rating.average}}</p>
          <p><img :src="article.images.medium"></p> 
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
    border-bottom: solid 3px red;
    margin: 10px;
    }
    li:hover {
    color: black;
    }
</style>

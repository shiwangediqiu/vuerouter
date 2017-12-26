<template>
  <main-layout>
    <div class="main"> 
      <div>
        <div v-for="(article,index) in articles" class="list">
          <h3>第{{index+201}}名</h3>
          <p>电影名：{{article.title}}</p>
          <p>上映时间：{{article.year}}  分类：{{article.genres[0]}}、{{article.genres[1]}}</p>
          <p><span>导演：</span><span v-for='article2 in article.directors'>{{article2.name}}</span></p>
          <p><span>主演：</span><span v-for="(article3,index) in article.casts">{{article3.name}}<span
              v-if='index < article.casts.length -1'>/</span></span></p>
          <p>评分：最高--{{article.rating.max}}，最低--{{article.rating.min}}，平均--{{article.rating.average}}</p>
          <p><img :src="article.images.medium"></p> 
        </div>
      </div>
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
    this.$http.jsonp('https://api.douban.com/v2/movie/top250?start=200&count=50', {}, {
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
      border: solid 1px #c8ffff;
      height: auto;
      width: 40%;
      margin: auto;
      text-align: center;
      font-size: 20px;
      color: #969696;
      background-color: #c8ffff;
    }
    .list {
    width: 75%;  
    padding-top: 0px;
    list-style: none;
    margin:20px auto;
    text-align: center;
    box-shadow:20px 0px 30px 10px #abcdef  inset;
    padding: 10px 0;
    }
    .list:hover {
    color: black;
    }
</style>

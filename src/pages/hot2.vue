<template>
    <div>
      <div class="head">
        <<span>热映电影排行榜</span>
      </div>
      <div>
        <ul class="ul">
        <li class="li"><v-link href="/hot1">第1页</v-link></li>
        <li class="li"><v-link href="/hot2">第2页</v-link></li>
      </ul>
      </div>      

      <slot></slot> 

      <div class="main">
        <div v-for="(article,index) in articles" class="list">
          <h3>第{{index+21}}名</h3>
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
</template>

<script>
  import moviepages from '../pages/movie.vue'
  import VLink from '../components/VLink.vue'

  export default {
    components: {
      moviepages,
      VLink
    },

    data() {
    return {
      articles: []
      }
    },
  
    mounted: function() {
    this.$http.jsonp('https://api.douban.com/v2/movie/in_theaters?count=20&start=20', {}, {
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

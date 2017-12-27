<template>
    <main-layout>
      <div class="main">
        <div class="body">
          <div class="bodytop">
            <div id="topleft">热映电影</div>
            <div id="topright"><span><v-link href="/hot1">更多></v-link></span></div>
          </div>
          <div class="bodyitem">
            <div class="item">
              <div v-for='item in movieList1'>
                <img :src="item.images.small">
                <p>{{item.title}}</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in movieList2'>
                <img :src="item.images.small">
                <p>{{item.title}}</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in movieList3'>
                <img :src="item.images.small">
                <p>{{item.title}}</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in movieList4'>
                <img :src="item.images.small">
                <p>{{item.title}}</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
              </div>
            </div>
          </div>
        </div>

        <div class="body">
          <div class="bodytop">
            <div id="topleft">即将上映</div>
            <div id="topright"><span><v-link href="/0-50">更多></v-link></span></div>
          </div>
          <div class="bodyitem">
            <div class="item">
              <div v-for='item in movieSoonList1'>
                <img :src="item.images.small">
                <p>{{item.title}}</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in movieSoonList2'>
                <img :src="item.images.small">
                <p>{{item.title}}</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in movieSoonList3'>
                <img :src="item.images.small">
                <p>{{item.title}}</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in movieSoonList4'>
                <img :src="item.images.small">
                <p>{{item.title}}</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
              </div>
            </div>
          </div>
        </div>

        <div class="body">
          <div class="bodytop">
            <div id="topleft">精选榜单</div>
          </div>
          <div class="bodyitem">
            <v-link href='/0-50' class="item" style="
            background-color: #e4cf6d">
              <h1>豆瓣top250</h1>
              <p>8分以上好电影</p>
            </v-link>
            <v-link href='/0-50' class="item" style="
            background-color: #ed3f62">
              <h1>热映榜</h1>
              <p>大家都在看</p>
            </v-link>            
            <v-link href='/0-50' class="item" style="
            background-color: #3cf0a4">
              <h1>即将上映</h1>
              <p>你所等待的</p>
            </v-link>            
          </div>
        </div>

      </div>  
    </main-layout>

</template>

<script>
  import VLink from '../components/VLink.vue'
  import MainLayout from '../layouts/Main.vue'

  export default {
    components: {
      VLink,
      MainLayout
    },
    data() {
      return {
        movieList1: [],
        movieList2: [],
        movieList3: [],
        movieList4: [],
        movieSoonList1: [],
        movieSoonList2: [],
        movieSoonList3: [],
        movieSoonList4: []
      }
    },
    mounted() {
      this.getHotMovie()
      this.getSoonMovie()
    },
    methods: {
      getHotMovie() {
        this.$http.jsonp('https://api.douban.com/v2/movie/in_theaters?count=1', {},{
          headers: {

          },
          emulateJSON: true
        }).then(function(response) {
          this.movieList1 = response.data.subjects
        }, function(response) {
          console.log(response)
        });
        
        this.$http.jsonp('https://api.douban.com/v2/movie/in_theaters?start=1&count=1', {},{
          headers: {

          },
          emulateJSON: true
        }).then(function(response) {
          this.movieList2 = response.data.subjects
        }, function(response) {
          console.log(response)
        });

        this.$http.jsonp('https://api.douban.com/v2/movie/in_theaters?start=2&count=1', {},{
          headers: {

          },
          emulateJSON: true
        }).then(function(response) {
          this.movieList3 = response.data.subjects
        }, function(response) {
          console.log(response)
        });

        this.$http.jsonp('https://api.douban.com/v2/movie/in_theaters?start=3&count=1', {},{
          headers: {

          },
          emulateJSON: true
        }).then(function(response) {
          this.movieList4 = response.data.subjects
        }, function(response) {
          console.log(response)
        });

      },
      
      getSoonMovie() {
        this.$http.jsonp('https://api.douban.com/v2/movie/coming_soon?count=1').then(response => {
          this.movieSoonList1 = response.data.subjects
          console.log(response)
        }, response => {

        });

        this.$http.jsonp('https://api.douban.com/v2/movie/coming_soon?start=1&count=1').then(response => {
          this.movieSoonList2 = response.data.subjects
          console.log(response)
        }, response => {

        });

        this.$http.jsonp('https://api.douban.com/v2/movie/coming_soon?start=2&count=1').then(response => {
          this.movieSoonList3 = response.data.subjects
          console.log(response)
        }, response => {

        });

        this.$http.jsonp('https://api.douban.com/v2/movie/coming_soon?start=3&count=1').then(response => {
          this.movieSoonList4 = response.data.subjects
          console.log(response)
        }, response => {

        });                
      }
    }
  }
</script>

<style>
  .main {
    border: solid 1px white;
    height: auto;
    width: 80%;
    margin: 0.1em auto; 
    background-color: white;
        }
  .body {
    border: solid 1px white;
    margin: 0.2em auto;
    width: 98%;
    height: auto;
    box-shadow: 0.05em 0.05em 0.2em 0.5em #abcdef  inset;
  }
  .bodytop {
    margin: 5px auto;
    width: 98%;
    height: 2em;
    font-size: 2em;
  }
  #topleft {
    margin-top: 0.2em;
    float:left;
  }
  #topright {
    margin-top: 0.2em;
    float: right;
  }
  .bodyitem {
    text-align: center;
    margin: 5px auto;
    width: 98%;
    height: 83%;
    font-size: 1.2em;
    display: flex;
    flex-flow: row || nowrap;
    justify-content: space-around; 
  }
  .item {
    border: solid 1px white;
    flex: 1;
    margin: 0.2em;
  }             
</style>

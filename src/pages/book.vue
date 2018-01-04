<template>
    <main-layout>
      <div class="main">
        <div class="body">
          <div class="bodytop">
            <div id="topleft">科学类</div>
            <div id="topright"><span><v-link href="/hot1">更多></v-link></span></div>
          </div>
          <div class="bodyitem">
            <div class="item">
              <div v-for='item in booksList1'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in booksList2'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in booksList3'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in booksList4'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>
          </div>
        </div>

        <div class="body">
          <div class="bodytop">
            <div id="topleft">文学类</div>
            <div id="topright"><span><v-link href="/coming1">更多></v-link></span></div>
          </div>
          <div class="bodyitem">
            <div class="item">
              <div v-for='item in booklList1'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in booklList2'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in booklList3'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in booklList4'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>
          </div>
        </div>

        <div class="body">
          <div class="bodytop">
            <div id="topleft">编程类</div>
            <div id="topright"><span><v-link href="/coming1">更多></v-link></span></div>
          </div>
          <div class="bodyitem">
            <div class="item">
              <div v-for='item in bookpList1'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in bookpList2'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in bookpList3'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
              </div>
            </div>

            <div class="item">
              <div v-for='item in bookpList4'>
                <img :src="item.image">
                <p>《{{item.title}}》</p>
                <p>最高评分：{{item.rating.max}}，最低评分：{{item.rating.min}}</p>
                <p>平均评分：{{item.rating.average}}</p>
                <p><span v-if="item.author != ''">作者：{{item.author[0]}}</span><span v-if="item.translator != ''">，翻译：{{item.translator[0]}} {{item.translator[1]}}</span></p>
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
            <v-link href='/hot1' class="item" style="
            background-color: #ed3f62">
              <h1>热映榜</h1>
              <p>大家都在看</p>
            </v-link>            
            <v-link href='/coming1' class="item" style="
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
        booksList0: [],
        booksList1: [],
        booksList2: [],
        booksList3: [],
        booksList4: [],
        booklList0: [],
        booklList1: [],
        booklList2: [],
        booklList3: [],
        booklList4: [],
        bookpList1: [],
        bookpList2: [],
        bookpList3: [],
        bookpList4: []
      }
    },
    mounted() {
      this.getScienceBook()
      this.getLetterBook()
      this.getProgrammeBook()
    },
    methods: {
      getScienceBook() {
        this.$http.jsonp('https://api.douban.com/v2/book/search?q=科学&count=1&start=0', {},{
          headers: {

          },
          emulateJSON: true
        }).then(function(response) {
          this.booksList1 = response.data.books
        }, function(response) {
          console.log(response)
        });
        
        this.$http.jsonp('https://api.douban.com/v2/book/search?q=科学&start=1&count=1', {},{
          headers: {

          },
          emulateJSON: true
        }).then(function(response) {
          this.booksList2 = response.data.books
        }, function(response) {
          console.log(response)
        });

        this.$http.jsonp('https://api.douban.com/v2/book/search?q=科学&start=2&count=1', {},{
          headers: {

          },
          emulateJSON: true
        }).then(function(response) {
          this.booksList3 = response.data.books
        }, function(response) {
          console.log(response)
        });

        this.$http.jsonp('https://api.douban.com/v2/book/search?q=科学&start=3&count=1', {},{
          headers: {

          },
          emulateJSON: true
        }).then(function(response) {
          this.booksList4 = response.data.books
        }, function(response) {
          console.log(response)
        });        

      },
      
      getLetterBook() {
        this.$http.jsonp('https://api.douban.com/v2/book/search?q=文学&count=1&start=0').then(response => {
          this.booklList1 = response.data.books
          console.log(response)
        }, response => {

        });

        this.$http.jsonp('https://api.douban.com/v2/book/search?q=文学&start=1&count=1').then(response => {
          this.booklList2 = response.data.books
          console.log(response)
        }, response => {

        });

        this.$http.jsonp('https://api.douban.com/v2/book/search?q=文学&start=2&count=1').then(response => {
          this.booklList3 = response.data.books
          console.log(response)
        }, response => {

        });

        this.$http.jsonp('https://api.douban.com/v2/book/search?q=文学&start=3&count=1').then(response => {
          this.booklList4 = response.data.books
          console.log(response)
        }, response => {

        });
                
      },

      getProgrammeBook() {
        this.$http.jsonp('https://api.douban.com/v2/book/search?q=编程&count=1&start=0').then(response => {
          this.bookpList1 = response.data.books
          console.log(response)
        }, response => {

        });

        this.$http.jsonp('https://api.douban.com/v2/book/search?q=编程&start=1&count=1').then(response => {
          this.bookpList2 = response.data.books
          console.log(response)
        }, response => {

        });

        this.$http.jsonp('https://api.douban.com/v2/book/search?q=编程&start=2&count=1').then(response => {
          this.bookpList3 = response.data.books
          console.log(response)
        }, response => {

        });

        this.$http.jsonp('https://api.douban.com/v2/book/search?q=编程&start=3&count=1').then(response => {
          this.bookpList4 = response.data.books
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
    background-color: #d3eea6;
  }
  .bodytop {
    margin: 5px auto;
    width: 98%;
    height: 2em;
    font-size: 1.5em;
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

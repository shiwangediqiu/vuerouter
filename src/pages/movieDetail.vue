<template>
  <div id='movieDetail' v-if='movie.title != null'>
    <div class="nav" v-if='large !="" '>
      <img class="nav-img" :src="large">
    </div>
    <div class="main">
      <div class="main-name">
        <div class="name">
          {{movie.title}}
        </div>
        <p>{{movieid}}</p>
        <div class="type">
          <span>{{movie.year}}/</span>
          <span v-for='item in movie.countries'>{{item}}/</span>
          <span v-for='(item,index) in movie.genres'>{{item}}<span v-if='index < movie.genres.length-1'>/</span></span>
        </div>
      </div>
      <div class="point">
        <div class="point_title">豆瓣评分</div>
        <div>
          <div class="point_rating">{{movie.rating.average}}</div>
          <div class="point_count" v-if='movie.rating.average > 0'>{{movie.collect_count}}</div>
          <div class="point_n" v-if='movie.rating.average === 0'>尚未上映</div>
        </div>
      </div>
    </div>

    <div class="review">
      <div>
        <button>想看{{movie.wish_count}}</button>
      </div>
      <div>
        <button>看过{{movie.reviews_count}}</button>
      </div>
    </div>

    <div class="desc">
      <div class="title">剧情简介</div>
      <div class="content">{{movie.summary}}</div>
    </div>
    <div class="director">
      <div class="title">影人</div>
      <div class="worker">
        <div v-for="item in movie.directors">
          <img :src="item.avatars.small" v-if="item.avatars.small">
          <div class="name" v-if="item.name">{{item.name}}</div>
        </div>
        <div v-for='item in movie.casts'>
          <img :src="item.avatars.small">
          <div class="name">{{item.name}}</div>
        </div>
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

    props: ["movieid"],

    data(){
      return {
        movie: {},
        large: '',
        filmName: '',
        average: '',
        isShow: false
      }
    },
    mounted(){
      this.getMovieDetail()
    },
    methods: {
      /**
       * 获取电影详情
       *
       * **/
      getMovieDetail(){
        this.$http.jsonp('https://api.douban.com/v2/movie/subject/1764796').then(response => {
          this.movie = response.data
          this.large = response.data.images.large
          this.average = response.data.rating.average
          this.filmName = response.data.title
        }, response => {

        })
      },
      backHome(){
        this.$router.go(-1)
      }
    },
  }

</script>
<style>
.main {
  margin: auto;
  text-align: center;     
}

</style>

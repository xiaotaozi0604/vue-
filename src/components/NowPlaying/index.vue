<template>
  <div class="movie_body">
    <ul v-for="item in movieLists" :key="item.id">
        <li>
          <div class="pic_show">图片</div>
          <div class="info_list">
            <h2>{{item.name}}</h2>
            <p>观众评<span class="grade">{{item.audienceRatings}}</span></p>
            <p>主演：{{item.starring}}</p>
            <p>{{item.describe}}</p>
          </div>
          <div class="btn_mall">购票</div>
        </li>
    </ul>
  </div>
</template>
<script>
import movieJson from "@/data/movieList.json";
const datas = movieJson;
export default {
  name: "NowPlaying",
  data() {
    return {
      movieLists: datas,
    };
  },
  methods: {
    getMovieList() {
      //   this.data.movieLists = [];
      //   const len = data.length;
    },
  },
  mounted() {
    console.log(this.movieLists);
  },
};
</script>
<style scoped>
#content .movie_body {
  flex: 1;
  overflow: auto;
}
.movie_body ul {
  margin: 0 12px;
  overflow: hidden;
}
.movie_body ul li {
  margin-top: 12px;
  display: flex;
  align-items: center;
  border-bottom: 1px solid #e6e6e6;
  padding-bottom: 10px;
}
.movie_body .pic_show {
  width: 64px;
  height: 90px;
  border: 1px solid red;
}
.movie_body .info_list {
  margin-left: 10px;
  flex: 1;
  position: relative;
}
.movie_body .info_list h2 {
  font-size: 17px;
  line-height: 24px;
  width: 150px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.movie_body .info_list p {
  font-size: 13px;
  color: #666;
  line-height: 22px;
  width: 200px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.movie_body .btn_mall {
  width: 47px;
  height: 27px;
  line-height: 28px;
  text-align: center;
  background-color: rosybrown;
  border-radius: 4px;
}
</style>

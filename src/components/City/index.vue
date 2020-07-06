<template>
  <div class="city_body">
    <div class="city_list">
      <div class="city_hot">
        <h2>热门城市</h2>
        <ul class="clearfix">
          <li v-for="item in hotCity.lists" :key="item">{{ item }}</li>
        </ul>
      </div>
      <div class="city_sort">
        <div v-for="item in sortCity" :key="item.title">
          <h2>{{item.title}}</h2>
          <ul>
            <li v-for="itemName in item.lists" :key="itemName">{{itemName}}</li>
          </ul>
        </div>
        <!-- <div>
          <h2>B</h2>
          <ul>
            <li>北京</li>
            <li>保定</li>
            <li>蚌埠</li>
            <li>宝鸡市</li>
            <li>保山市</li>
          </ul>
        </div>
        <div>
          <h2>C</h2>
          <ul>
            <li>长春市</li>
            <li>常德市</li>
            <li>沧州市</li>
            <li>朝阳市</li>
            <li>成都市</li>
          </ul>
        </div>
        <div>
          <h2>D</h2>
          <ul>
            <li>大连市</li>
            <li>丹东市</li>
            <li>儋州市</li>
            <li>大庆市</li>
            <li>大同市</li>
          </ul>
        </div> -->
      </div>
    </div>
    <div class="city_index">
      <ul v-for="item in cityList" :key="item.index">
        <li>{{ item.title }}</li>
      </ul>
    </div>
  </div>
</template>
<script>
import cityJson from "@/data/city.json";
const datas = cityJson;
export default {
  name: "City",
  data() {
    return {
      cityList: datas,
      hotCity: [],
      sortCity: [],
    };
  },
  mounted() {
    console.log(this.cityList);
    this.hotCity = this.cityList.find((item) => {
      return item.title === "热门城市";
    });
    this.sortCity = this.cityList.filter((item) => {
      return item.title !== "热门城市";
    });
    console.log(this.sortCity);
  },
};
</script>
<style>
#content .city_body {
  margin-top: 45px;
  display: flex;
  width: 100%;
  position: absolute;
  top: 0;
  bottom: 0;
}
.city_body .city_list {
  flex: 1;
  overflow: auto;
  background: #fff5f0;
}
.city_body .city_list::-webkit-scrollbar {
  background-color: transparent;
  width: 0;
}
.city_body .city_hot {
  margin-top: 20px;
}
.city_body .city_hot h2 {
  padding-left: 15px;
  line-height: 30px;
  font-size: 14px;
  background: #f0f0f0;
  font-weight: normal;
}
.city_body .city_hot ul li {
  float: left;
  background: #fff;
  width: 29%;
  height: 33px;
  margin-top: 15px;
  margin-left: 2%;
  padding: 0 4px;
  text-align: center;
  line-height: 33px;
}
.city_body .city_sort div {
  margin-top: 20px;
}
.city_body .city_sort h2 {
  padding-left: 15px;
  line-height: 30px;
  font-size: 14px;
  background: #f0f0f0;
  font-weight: normal;
}
.city_body .city_sort ul {
  padding-left: 10px;
  margin-top: 10px;
}
.city_body .city_sort ul li {
  line-height: 30px;
  /* border-bottom: 1px solid #e6e6e6; */
}
.city_body .city_index {
  width: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  border-left: 1px solid #e6e6e6;
}
</style>

<template>
  <div class="cinema_body">
    <ul>
      <li v-for="item in dataList" :key="item.id">
        <div>
          <span>{{item.name}}</span>
          <span class="q"><span class="price">{{item.price}}</span> 元起</span>
        </div>
        <div class="address">
          <span>{{item.address}}</span>
          <span>{{item.distance}}</span>
        </div>
        <div class="card">
            <div>小吃</div>
            <div>折扣卡</div>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
import cinemaCityJson from "@/data/cinemaCity.json";
const datas = cinemaCityJson;
export default {
  name: "CityList",
  data(){
      return{
          dataList:datas
      }
  }
};
</script>
<style scoped>
#content .cinema_body {
  flex: 1;
  overflow: auto;
}
.cinema_body ul {
  padding: 20px;
}
.cinema_body ul li {
  border-bottom: 1px solid #e6e6e6;
  margin-bottom: 20px;
}
.cinema_body div {
  margin-bottom: 10px;
}
.cinema_body .q {
  font-size: 11px;
  color: #f03d37;
}
.cinema_body .price {
  font-size: 18px;
  margin-left: 10px;
}
.cinema_body .address {
  font-size: 13px;
  color: #666;
}
.cinema_body .address span:nth-of-type(2) {
  float: right;
}
.cinema_body .card {
  display: flex;
}
.cinema_body .card div {
  padding: 0 30px;
  height: 15px;
  line-height: 15px;
  border-radius: 2px;
  color: #f90;
  border: 1px solid #f90;
  font-size: 13px;
  margin-right: 5px;
}
.cinema_body .card div.or {
  color: #f90;
  border: 1px solid #f90;
}
.cinema_body .card div.bl {
  color: #589daf;
  border: 1px solid #589daf;
}
</style>

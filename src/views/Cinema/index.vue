<template>
  <div id="main">
    <Header title="我的影院" />
    <div id="content">
      <div class="mine_menu">
        <div class="item" v-for="item in tabData" :key="item.index">
          <span>{{ item.name }}</span
          ><i class="iconfont icon-bofangjilu"></i>
        </div>
      </div>
      <CityList />
    </div>
    <tab-bar />
  </div>
</template>

<script>
import Header from "@/components/Header";
import TabBar from "@/components/TabBar";
import CityList from "@/components/CityList";
export default {
  data() {
    return {
      tabData: [
        { name: "全城", index: 0 },
        { name: "品牌", index: 1 },
        { name: "特色", index: 2 },
      ]
    };
  },
  name: "Cinema",
  components: {
    Header,
    TabBar,
    CityList,
  },
};
</script>
<style>
#content .mine_menu {
  width: 100%;
  height: 45px;
  border-bottom: 1px solid #e6e6e6;
  display: flex;
}
.mine_menu .item {
  margin: 0 20px;
  height: 100%;
  line-height: 45px;
  font-size: 16px;
  font-weight: normal;
  width: 33%;
  text-align: center;
}
.iconfont {
  margin-left: 5px;
}
</style>

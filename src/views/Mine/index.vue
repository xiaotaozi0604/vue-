<template>
  <div id="main">
    <Header title="我的影院" />
    <div id="content">
      <login />
    </div>
    <tab-bar />
  </div>
</template>

<script>
import Header from "@/components/Header";
import TabBar from "@/components/TabBar";
import login from "@/components/Login";
export default {
  name: "Mine",
  components: {
    login,
    Header,
    TabBar,
  },
  methods: {},
};
</script>
<style></style>

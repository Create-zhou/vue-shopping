
<template>
  <common-nav-bar>
    <template #left>
      <img src="~assets/img/common/back.svg" @click="goback" />
    </template>
    <template #middle>
      <ul class="nav-bar-title">
        <li v-for="(item,index) in titles"
         :key="index" 
         @click="handleClick(index)"
         :class="{active:currentIndex===index}">
          {{item}}
        </li>
      </ul>
    </template>
  </common-nav-bar>
</template>

<script>
export default {
  name: "detailnavbar",
  data() {
    return {
      titles: ["商品", "参数", "评论", "推荐"],
      currentIndex:0
    };
  },
  methods: {
    goback() {
      this.$router.go(-1);
    },
    handleClick(index){
        this.currentIndex = index
    }
  }
};
</script>

<style scoped lang='less'>
 .nav-bar-title {
   display:flex;
    font-size: 14px;

  }
  
  .nav-bar-title li {
    flex: 1;
  }
  
  .active {
    color: red;
    font-weight:bold;
    font-size: 16px;
    border-bottom: 3px solid red;
  }
  
  img {
    margin-top: 12px;
    width: 20px;
  }
</style>
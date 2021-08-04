<template>
<div id="detail">
<detail-nav-bar/>
<detail-swiper :top-images="topImages"/>
</div>
</template>

<script>
import DetailNavBar from './childComps/DetailNavBar.vue'
import DetailSwiper from './childComps/DetailSwiper.vue'

import {getDetail} from '../../network/detail'

export default {
       name:"Detail",
  components: {DetailNavBar,DetailSwiper,},
  data() {
    return {
        iid:null,
        topImages:[]
    };
  },
  created() {
    // 1.保存传入的iid
      this.iid = this.$route.params.iid
      // console.log(this.$route.params);

    // 2.根据iid请求详情数据
      getDetail(this.iid).then(res=>{
        // 1.获取顶部的图片轮播图数据
        console.log(res);
        this.topImages = res.result.itemInfo.topImages
        console.log(this.topImages );
      })
  },
  mounted() {},
  computed: {},
  methods: {},
};
</script>
<style lang="scss" scoped>

</style>
<template>
 <div>
    <h2  @click="fun" >分类</h2>
    <!-- <router-link to="/news">分类</router-link> -->
    <div>123</div>
    <router-view></router-view>
 </div>

</template>

<script>
export default {
methods:{
  fun(){
    this.$router.push('/news')
  }
}
}
</script>

<style>

</style>
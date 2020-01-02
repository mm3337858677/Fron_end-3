<template>
 <el-container>
  <el-header>
  	<el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
  <el-menu-item index="1">客服中心</el-menu-item>
  <el-submenu index="2">
    <template slot="title">我的购物车</template>
    <el-menu-item index="2-1">喜欢</el-menu-item>
    <el-menu-item index="2-2">收藏</el-menu-item>
    <el-menu-item index="2-3">已选</el-menu-item>
  </el-submenu>
  <el-menu-item index="3"><a href="" target="_blank">消息中心</a></el-menu-item>
  <el-menu-item index="4"><a href="" target="_blank">好物推荐</a></el-menu-item>
</el-menu>
<div class="line"></div>
  </el-header>
  <el-container>
    <el-aside width="400px">
    	<el-col :span="12">
    <h5>默认颜色</h5>
    <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose">
      <el-submenu index="1">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span>运动</span>
        </template>
        <el-menu-item-group>
          <template slot="title">男生</template>
          <el-menu-item index="1-1">服饰</el-menu-item>
          <el-menu-item index="1-2">鞋帽</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="女生">
          <el-menu-item index="1-3">服饰</el-menu-item>
          <el-menu-item index="1-4">鞋帽</el-menu-item>
        </el-menu-item-group>
      </el-submenu>
      <el-menu-item index="2">
        <i class="el-icon-menu"></i>
        <span slot="title">美食</span>
      </el-menu-item>
      <el-menu-item index="3">
        <i class="el-icon-document"></i>
        <span slot="title">学习</span>
      </el-menu-item>
      <el-menu-item index="4">
        <i class="el-icon-setting"></i>
        <span slot="title">家电</span>
      </el-menu-item>
    </el-menu>
  </el-col>
    	</el-aside>
    <el-container>
      <el-main>
      	<div class="imgbox">
  		<img src="../../../assets/img/1.jpg">
			<img src="../../../assets/img/2.jpg">
			<img src="../../../assets/img/3.jpg">
			<img src="../../../assets/img/4.jpg">
			<img src="../../../assets/img/5.jpg">
				</div>
     </el-main>
    </el-container>
  </el-container>
</el-container>
</template>

<script>
//	export default {
//  methods: {
//    handleOpen(key, keyPath) {
//      console.log(key, keyPath);
//    },
//    handleClose(key, keyPath) {
//      console.log(key, keyPath);
//    }
//  }
//}
export default {
data () {
    return {
      lists:[
        {title:'学习',icon:'icontongxunlu'},
        {title:'电影',icon:'iconfaxian'},
        {title:'娱乐',icon:'iconshouye1'},
        {title:'运动',icon:'iconcompass'},
        {title:'家电',icon:'iconfenlei'},
        {title:'服饰',icon:'iconfenlei'},
        {title:'休闲',icon:'iconfenlei'},
        {title:'美食',icon:'iconfenlei',color:'#fa69b9'}
      ]
    }
}
}
//export default {
//data () {
//  return {
//    n: 0
//  }
//},
//props:['img'],  //父到子传参数
//  methods:{
//      fun:function(){
//          //setInterval(函数体,时间)
//          setInterval(this.play,2000)
//      },
//      play:function(){
//          this.n++;
//          if(this.n == this.img.length){
//              this.n = 0;
//          }
//      }
//  },
//  mounted:function(){    //生命周期  钩子函数   挂载完成
//      this.fun()
//  }
//}


</script>


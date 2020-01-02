<template>
	 <el-container>
  <el-header>
  	<el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
  <el-submenu index="1">
    <template slot="title">客服中心</template>
    <el-menu-item index="1-1">投诉</el-menu-item>
    <el-menu-item index="1-2">举报</el-menu-item>
    <el-menu-item index="1-3">咨询</el-menu-item>
  </el-submenu>
  <el-submenu index="2">
    <template slot="title">我的购物车</template>
    <el-menu-item index="2-1">喜欢</el-menu-item>
    <el-menu-item index="2-2">收藏</el-menu-item>
    <el-menu-item index="2-3">已选</el-menu-item>
  </el-submenu>
  <el-submenu index="3">
    <template slot="title">消息中心</template>
    <el-menu-item index="3-1">已读</el-menu-item>
    <el-menu-item index="3-2">未读</el-menu-item>
    <el-menu-item index="3-3">回收站</el-menu-item>
  </el-submenu>
  <el-submenu index="4">
    <template slot="title">好物推荐</template>
    <el-menu-item index="4-1">猜你喜欢</el-menu-item>
    <el-menu-item index="4-2">排行榜</el-menu-item>
    <el-menu-item index="4-3">大家都买</el-menu-item>
  </el-submenu>
  <el-submenu index="5">
    <template slot="title">明星周边</template>
    <el-menu-item index="5-1">猜你喜欢</el-menu-item>
    <el-menu-item index="5-2">排行榜</el-menu-item>
    <el-menu-item index="5-3">大家都买</el-menu-item>
    
  </el-submenu>
  
  <el-col :span="4"><div class="grid-content bg-purple">
  	<el-input v-model="input" placeholder="请输入你要查找的宝贝">
  	</el-input>
  </div></el-col>
  <el-col :span="1"><div class="grid-content bg-purple-light">
  	<el-button icon="el-icon-search" circle></el-button>
  </div></el-col>
 
  
  

</el-menu>
<div class="line"></div>
  </el-header>
  <el-container>
    <el-aside width="100px">
    	<el-col :span="12">
    <h5>默认颜色</h5>
    <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose">
      <el-menu-item index="1">
        <i class="el-icon-location"></i>
        <span slot="title">运动</span>
      </el-menu-item>
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
      <el-menu-item index="5">
        <i class="el-icon-setting"></i>
        <span slot="title">科技</span>
      </el-menu-item>
    </el-menu>
  </el-col>
    	</el-aside>
    <el-container>
      <el-main>
      	<div>
        <div class="banner">
            <img  v-for="(v,i) in img " :key="i" :src="v" v-show="i==n"/>   
            <div class="banner-circle">
                <ul>
                    <li  v-for="(v,i) in img " :key="i" :class="i==n ?'selected':''"></li>  
                </ul> 
            </div>
        </div>
  </div>
     </el-main>
     <el-aside width="100px">
     	<el-radio-group v-model="isCollapse" style="margin-bottom: 10px;">
</el-radio-group>
<el-menu default-active="1-4-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
  <el-submenu index="1">
    <template slot="title">
      <i class="el-icon-location"></i>
      <span slot="title">导航一</span>
    </template>
    <el-menu-item-group>
      <span slot="title">分组一</span>
      <el-menu-item index="1-1">选项1</el-menu-item>
      <el-menu-item index="1-2">选项2</el-menu-item>
    </el-menu-item-group>
    <el-menu-item-group title="分组2">
      <el-menu-item index="1-3">选项3</el-menu-item>
    </el-menu-item-group>
    <el-submenu index="1-4">
      <span slot="title">选项4</span>
      <el-menu-item index="1-4-1">选项1</el-menu-item>
    </el-submenu>
  </el-submenu>
  <el-menu-item index="2">
    <i class="el-icon-menu"></i>
    <span slot="title">导航二</span>
  </el-menu-item>
  <el-menu-item index="3">
    <i class="el-icon-document"></i>
    <span slot="title">导航三</span>
  </el-menu-item>
  <el-menu-item index="4">
    <i class="el-icon-setting"></i>
    <span slot="title">导航四</span>
  </el-menu-item>
</el-menu>
     	</el-aside>
    </el-container>
  </el-container>
</el-container>
  <!--<div>
        <div class="banner">
            <img  v-for="(v,i) in img " :key="i" :src="v" v-show="i==n"/>   
            <div class="banner-circle">
                <ul>
                    <li  v-for="(v,i) in img " :key="i" :class="i==n ?'selected':''"></li>  
                </ul> 
            </div>
        </div>
  </div>-->
</template>

<script>
export default {
  data () {
    return {
      n: 0
    }
  },
  props:['img'],  //父到子传参数
    methods:{
        fun:function(){
            //setInterval(函数体,时间)
            setInterval(this.play,2000)
        },
        play:function(){
            this.n++;
            if(this.n == this.img.length){
                this.n = 0;
            }
        }
    },
    mounted:function(){    //生命周期  钩子函数   挂载完成
        this.fun()
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*{
    margin:0;
    padding:0;
}
ul {
    list-style-type:none;
}
body {
    font-size: 14px;
    background: #fff;
    overflow-y:scroll;
    overflow-x:hidden;
}
html,body {
    max-width:720px;
    height:100%;
    margin:0 auto;
}

/*index*/
.banner {
    position: relative;
}
.banner .banner-circle {
    position: absolute;
    bottom: 5px;
    left: 0;
    right: 0;
    color: #fff;
}
.banner .banner-circle li{
    display:inline-block;
    background: rgba(0,0,0,.3);
    border-radius: 50%;
    padding:5px;
    margin:2px;
}
.banner .banner-circle ul {
    text-align: center;
}
.banner .banner-circle .selected {
    background: rgba(0,0,0,.8);
}
.index-content .banner img {
    width: 100%;
    margin: 0;
    padding: 0;
}
</style>

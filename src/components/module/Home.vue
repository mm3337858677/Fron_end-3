<template>
  <div>
      <Category />
      <Banner :img="img"/>
      <div class="index-main">
        <ul>
            <li class="lists" v-for="(item,index) in items" :key="index">
                <router-link :to="'/detail/'+item.id">
                  <img :src="item.img" width="150" height="150">
                </router-link>
                <label>
                     <span >商品名：{{item.shopname}}</span> 
                     </br>
                    <b class="discount">折扣价： {{item.saleprice}}</b>
                    <span class="price-text">原价： {{item.price}}</span> 
                </label>            
            </li> 
        </ul>  
    </div>
  </div>
</template>

<script>
import Banner from './common/Banner';   //引入组件
import Category from './common/Category';   //引入组件
import nav from './nav';
import axios from 'axios';

export default {
  data () {
    return {
      img: [require("@/assets/img/1.jpg"),
            require("@/assets/img/2.jpg"),
            require("@/assets/img/3.jpg"),
            require("@/assets/img/4.jpg"),
            require("@/assets/img/5.jpg"),
            require("@/assets/img/6.jpg")],
      items: []
    }
  },
   components: { 
    Banner,
//  Category
  },
  methods:{ //方法
    getData:function(){
     axios.get("api/list").then(res=>{
        console.log(res);
        if(res.status =='200'){
          this.items = res.data;
        }
      },(error)=>{
        console.log(error)
      })
    }
  },
  mounted:function(){    //生命周期
    this.getData();
  }
}


</script>



<template>
  <div>
      <Category />
      <Banner :img="img"/>
      <div class="index-main">
        <ul>
            <li class="lists" v-for="(item,index) in items" :key="index">
               
                  <img :src="item.img" width="150" height="150">
               
                <label>
                    <b class="discount">折扣价： {{item.price}}</b>
                    <span class="price-text">原价： {{item.shopname}}</span> 
                </label>            
            </li> 
        </ul>  
    </div>
  </div>
</template>

<script>
import Banner from './common/Banner';   //引入组件
import Category from './common/Category';   //引入组件
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
   
  methods:{ //方法
    getData:function(){
     var newsID=this.$route.query.id
     axios.get("api/list?id="+newsID).then(res=>{
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



<template>

  <div >
    <div  class="top">
<li>1</li>
<li>2</li>
<li>3</li>
<li>4</li>
</div>
      <div class="index-main"  >
        
            <li class="lists" v-for="(item,index) in items" :key="index">
                <router-link :to="'/detail/'+item.id">
                  <img :src="item.img" width="150" height="150">
                </router-link>
                <label>
                    <b class="discount">商品编号： {{item.id}}</b>
                    <span class="price-text">商品名称： {{item.shopname}}</span> 
                    
                </label>
                   <label>
                      <span class="price-text">原价： {{item.price}}</span>
                      <span class="price-text">打折价： {{item.saleprice}}</span>
                </label>  

            </li> 
       
    </div>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  data () {
    return {
      
      items: []
    }
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


<style>
   .top li {
	float: left;
	list-style-type: none;
	padding-right: 5px;
	padding-left: 5px;
}


</style>
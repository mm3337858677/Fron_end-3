<template>
<div  style="display=block" >

<div class="div-a"    v-for="(item,index) in items" :key="index"> 
         
                <router-link :to="'/detail/'+item.id">
                  <img :src="item.img" width="150" height="150" margin-left=140px>
                </router-link>
                 
     <div style="float:right" >
                <label>
                    <img :src="item.img" width="150" height="150" margin-left=140px>
                    <b class="discount">商品编号： {{item.id}}</b></br>
                    <span class="price-text">商品名称： {{item.shopname}}</span> 
                  
                </label></br>
                   <label>
                      <span class="price-text">原价： {{item.price}}</span></br>
                      <span class="price-text">打折价： {{item.saleprice}}</span>
                </label>
                </br>  
                </br> 
         </div>
          
  </div> 
 
 </br> 

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


<style > 
.div-a{ float:left;width:35%;height:300px;} 
 
</style> 
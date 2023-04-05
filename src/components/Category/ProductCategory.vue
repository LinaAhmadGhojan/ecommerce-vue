<template>
   <!-- electronic section start -->
 <div class="fashion_section">
    <div id="electronic_main_slider" class="carousel slide" data-ride="carousel">
       <div class="carousel-inner">
          <div class="carousel-item active">
             <div class="container">
                <h1 class="fashion_taital">{{category}}</h1>
                <div class="fashion_section_2">
                   <div class="row">
                    
                      <div v-for="product in products"  class="col-lg-4 col-sm-4">
                         <div class="box_main">
                            <h4 class="shirt_text">{{product.title}}</h4>
                            <p class="price_text">Start Price  <span style="color: #262626;">$ {{product.price}}</span></p>
                            <div class="electronic_img"><img  class="img_product" :src="product.image"></div>
                            <div class="btn_main">
                               <div class="buy_bt"><a href="#">Buy Now</a></div>
                               <div class="seemore_bt"><a href="#">See More</a></div>
                            </div>
                         </div>
                      </div>
       
                   </div>
                </div>
             </div>
          </div>
        


       </div>
   
    </div>
 </div>


 
</template>


<script>
import axios from 'axios'
const baseUrl="https://fakestoreapi.com";
export default {
  data: function()
 { 
  return {
    pagename:"home",
    pagedescription:"This is an home page",
    products:[]
  
  } ;
},
props:["category"]
,

name:"home",
mounted() {
     
    axios.get(baseUrl+'/products/category/'+this.category)
      .then(response => {
        this.products = response.data
        console.log("true products");
      })
      .catch(error => {
        console.log(error)
      })
  }
    
  }


</script>

<style>
.img_product {
    max-width: 100%;
    height: 341px;
}
</style>
<template>
   <!-- banner bg main start -->
   <div class="banner_bg_main">
    <!-- header top section start -->

    <!-- header top section start -->
    <!-- logo section start -->
    <div class="logo_section">
       <div class="container">
          <div class="row">
             <div class="col-sm-12">
                <div class="logo"><a href="index.html"><img src="../assets/image/logo.png"></a></div>
             </div>
          </div>
       </div>
    </div>
    <!-- logo section end -->
    <!-- header section start -->
    <div class="header_section">
       <div class="container">
          <div class="containt_main">
            
             <span class="toggle_icon" onclick="openNav()"><img src="../assets/image/toggle-icon.png"></span>
             <div class="dropdown">
                <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">All Category 
                </button>
              
             </div>
             <div class="main">
                <!-- Another variation with a button -->
                <div class="input-group">
                   <input type="text" class="form-control" placeholder="Search this blog">
                   <div class="input-group-append">
                      <button class="btn btn-secondary" type="button" style="background-color: #f26522; border-color:#f26522 ">
                      <i class="fa fa-search"></i>
                      </button>
                   </div>
                </div>
             </div>
             <div class="header_box">
                <div class="lang_box ">
                   <a href="#" title="Language" class="nav-link" data-toggle="dropdown" aria-expanded="true">
                   <img src="../assets/image/flag-uk.png" alt="flag" class="mr-2 " title="United Kingdom"> English <i class="fa fa-angle-down ml-2" aria-hidden="true"></i>
                   </a>
                   <div class="dropdown-menu ">
                      <a href="#" class="dropdown-item">
                      <img src="../assets/image/flag-france.png" class="mr-2" alt="flag">
                      French
                      </a>
                   </div>
                </div>
                <div class="login_menu">
                   <ul>
                      <li><a href="#">
                         <i class="fa fa-shopping-cart" aria-hidden="true"></i>
                         <span class="padding_10">Cart</span></a>
                      </li>
                      <li><a href="#">
                         <i class="fa fa-user" aria-hidden="true"></i>
                         <span class="padding_10">Cart</span></a>
                      </li>
                   </ul>
                </div>
             </div>
          </div>
       </div>
    </div>
    <!-- header section end -->
    <!-- banner section start -->
    <div class="banner_section layout_padding">
       <div class="container">
          <div id="my_slider" class="carousel slide" data-ride="carousel">
             <div class="carousel-inner">
                <div class="carousel-item active">
                   <div class="row">
                      <div class="col-sm-12">
                         <h1 class="banner_taital">Get Start <br>Your favriot shoping</h1>
                         <div class="buynow_bt"><a href="#">Buy Now</a></div>
                      </div>
                   </div>
                </div>
                <div class="carousel-item">
                   <div class="row">
                      <div class="col-sm-12">
                         <h1 class="banner_taital">Get Start <br>Your favriot shoping</h1>
                         <div class="buynow_bt"><a href="#">Buy Now</a></div>
                      </div>
                   </div>
                </div>
                <div class="carousel-item">
                   <div class="row">
                      <div class="col-sm-12">
                         <h1 class="banner_taital">Get Start <br>Your favriot shoping</h1>
                         <div class="buynow_bt"><a href="#">Buy Now</a></div>
                      </div>
                   </div>
                </div>
             </div>
             <a class="carousel-control-prev" href="#my_slider" role="button" data-slide="prev">
             <i class="fa fa-angle-left"></i>
             </a>
             <a class="carousel-control-next" href="#my_slider" role="button" data-slide="next">
             <i class="fa fa-angle-right"></i>
             </a>
          </div>
       </div>
    </div>
    <!-- banner section end -->
 </div>

 <ProductCategory v-for="category in categories" :category="category" />



 <div class="footer_section layout_padding">
    <div class="container">
       <div class="footer_logo"><a href="index.html"><img src="../assets/image/footer-logo.png"></a></div>
       <div class="input_bt">
          <input type="text" class="mail_bt" placeholder="Your Email" name="Your Email">
          <span class="subscribe_bt" id="basic-addon2"><a href="#">Subscribe</a></span>
       </div>
       <div class="footer_menu">
          <ul>
             <li><a href="#">Best Sellers</a></li>
             <li><a href="#">Gift Ideas</a></li>
             <li><a href="#">New Releases</a></li>
             <li><a href="#">Today's Deals</a></li>
             <li><a href="#">Customer Service</a></li>
          </ul>
       </div>
       <div class="location_main">Help Line  Number : <a href="#">+1 1800 1200 1200</a></div>
    </div>
 </div>
 <!-- footer section end -->
 <!-- copyright section start -->
 <div class="copyright_section">
    <div class="container">
       <p class="copyright_text">© 2020 All Rights Reserved. Design by <a href="https://html.design">Free html  Templates</a></p>
    </div>
 </div>
</template>

<script>
import axios from 'axios'
import ProductCategory from '../components/Category/ProductCategory.vue';
const baseUrl="https://fakestoreapi.com";
export default {
  data: function()
 { 
  return {
    pagename:"home",
    pagedescription:"This is an home page",
    categories:[]
  } ;
},
components:{
  ProductCategory
},

name:"home",
mounted() {
    axios.get(baseUrl+'/products/categories')
      .then(response => {
        this.categories = response.data
        console.log("true category");
      })
      .catch(error => {
        console.log(error)
      })
  }
    
  }


</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }

 
  .class-home{
    text-align: center;
  }
}
</style>
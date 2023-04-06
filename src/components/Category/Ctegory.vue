<template>
    <div  class="col-lg-3 col-md-4 col-sm-6 pb-1">
   
        <a class="text-decoration-none" href="">
            <div class="cat-item d-flex align-items-center mb-4">
                <div class="overflow-hidden" style="width: 100px; height: 100px;">
                </div>
                <div class="flex-fill pl-3">
                    <h6>{{category}}</h6>
                </div>
            </div>
        </a>
        </div>
    
</template>

<script>
export default {
    data: function()
 { return {} ;},

 props:["category"]


}
</script>
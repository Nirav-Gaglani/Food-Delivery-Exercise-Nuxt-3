<template>
<section class="container-lg mt-1 mb-4 pt-1">
    <div class="row mt-2 d-flex justify-content-between">
        <div v-for="i, index in 20" :key="index" class="card col-md-3 col-xs-4 p-3 border border-2 mt-4">
                <img src="../assets/card-1-image.png" alt="" class="card-img-top image-fluid mt-2" width="100%" height="auto">
                <h3 class="card-title">{{props.data[i].RestaurantName}}</h3>
                <h6 class="card-subtitle text-muted">{{props.data[i].Address}}</h6>
                <div class="card-body p-0 pt-2 mb-2">
                    <ul class="list-unstyled">
                        <li>Restaurant Status: Available</li>
                        <li>Sr.No. {{props.data[i].Sr_No}}</li>
                        <li>Votes: 1256</li>
                    </ul>
                    <a href="#" class="btn btn-danger">Order</a>
                </div>
        </div>
    
            <!-- <div class="card col-md-3 col-xs-6 mx-4 border">
                <img src="../assets/card-2-image.png" alt="" class="card-img-top image-fluid mt-2" width="100%" height="auto">
                <h3 class="card-title">Temptation</h3>
                <h6 class="card-subtitle text-muted">Kotecha Nagar Rajkot, Nirmala Convent Road</h6>
                    <div class="card-body p-0 pt-2 mb-2">
                        <ul class="list-unstyled">
                            <li>Restaurant Status: Available</li>
                            <li>Ratings: 4.5/5</li>
                            <li>Votes: 1554</li>
                        </ul>
                    <a href="#" class="btn btn-danger">Open</a>
                </div>
            </div> -->
    
            <!-- <div class="card col-md-3 col-xs-6 mx-4 border">
                <img src="../assets/card-3-image.png" alt="" class="card-img-top image-fluid mt-2" width="100%" height="auto">
                <h3 class="card-title">Chwoki Dhani</h3>
                <h6 class="card-subtitle text-muted">Kotecha Nagar Rajkot, Nirmala Convent Road</h6>
                    <div class="card-body p-0 pt-2 mb-2">
                        <ul class="list-unstyled">
                            <li>Restaurant Status: Available</li>
                            <li>Ratings: 4.0/5</li>
                            <li>Votes: 992</li>
                        </ul>
                    <a href="#" class="btn btn-danger">Open</a>
                </div>
            </div> -->
        </div>
</section>
</template>

<script setup>
const props = defineProps({
    data: Array
})
</script>
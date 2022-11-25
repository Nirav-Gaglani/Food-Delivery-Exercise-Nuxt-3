git@github.com:Nirav-Gaglani/Food-Delivery-Exercise-Nuxt-3.git
<template>
  <main class="mt-0 mb-1 pt-1">
    <section class="bgSPImage">
      <div class="container-lg">
        <div class="mt-4 pt-4 w-50 text-white">
            <h1>Discover Best Restaurants Delevering near you</h1>
        </div>
          <div class="row d-flex justify-content-between h3 mt-lg-5 mt-sm-2 pt-md-5 pt-sm-3">
                <div class="col-md-2 col-3 p-0 d-inline-block">

                  <select v-for="(city, index) in cityList" :key="index" class="form-select" aria-label="Default select example">
  <option selected>Open this select menu</option>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>
                  <!-- <input type="text" placeholder="Location" class="form-control" id="search" name="city"> -->
                  <!-- <select v-for="city, index in cityList" :key="index" placeholder="City" class="form-control" id="exampleFormControlSelect1" name="city"> -->
                  <!-- <select placeholder="City" class="form-control" id="exampleFormControlSelect1" name="city"> -->
                      <!-- <option>Nirav</option> -->
                      <!-- <option selected>London</option>
                      <option>Boston</option>
                      <option>Mumbai</option>
                      <option>New York</option>
                      <option>Toronto</option>
                      <option>Paris</option> -->
                  <!-- </select> -->
                  
                  <!-- <button class="btn btn-danger dropdown-toggle me-2" type="button" name="Cuisines" data-bs-toggle="dropdown" aria-expanded="false">
                        Cuisine
                    </button>
        <ul class="dropdown-menu">
            <li v-for="city, index in cityList" :key="index">{{city}}</li>
        </ul> -->
                </div>
                <div class="col-md-4 col-3 p-0 d-inline-block">
                    <input type="text" placeholder="Search Cuisine" class="form-control" id="search" name="cuisine">
                </div>
                <div class="col-1 p-0 d-inline-block">
                    <button type="submit" class="btn btn-danger ms-1">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-search"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
                    </button>
                </div>
        </div>
    </div>
  </section>
</main>
</template>

<style>
.bgSPImage{ 
    background: linear-gradient(rgba(25, 25, 25, 0.7),
                    rgba(25, 25, 25, 0.7)), url("../assets/background.jpg")no-repeat center center/cover;
    height: 50vh;
}
</style>

<script setup>
const props = defineProps({
  data: Array
});
let duplicatedCityList, cityList;
duplicatedCityList = await getCityArr(props.data);
cityList = await removeDuplicates(duplicatedCityList);

// getRestroArr(props.data)
// .then((restroArr)=>removeDuplicates(restroArr))
// .then((uniQ)=>console.log(uniQ))

function getCityArr(data){
  let promise = new Promise(function(resolve, reject){
  let restroArr=[];
  data.forEach(restro => {
      restroArr.push(restro.City);
  });
  resolve(restroArr);
})
  return promise
}

function removeDuplicates(data) {
  let uniQ = data.filter((item,
      index) => data.indexOf(item) === index);
  return uniQ
}
</script>

<template>
  <div class="container rounded p-3 mt-3">
  <div class="row shadow halamanHome rounded">
    <div class="col">
      <div class="content">
        <h3>Super value <span>deals</span></h3>
        <h4>On all products</h4 >
        <p class="paragraf">Temukan barang yang anda suka di website ini</p>
        <router-link to="/products" class="btn btn-danger">Go Shop</router-link>
      </div>
    </div>
  </div>
</div>
  <!-- about -->
<AboutProduct />

<FooterHome/>

</template>

<script>
import AboutProduct from "../components/AboutProduct.vue"
import FooterHome from "../components/Footers.vue"
export default{
  components:{
    AboutProduct,
    FooterHome
  }
}
</script>

<style>
.halamanHome {
  background-image: url(../assets/hero4.png);
  height: 90vh;
  background-position: center;
  background-size: cover;
}
.content {
  margin-top: 200px;
  margin-left: 100px;
}
img{
  height: 40vh;
}
h3{
  font-size: 4em;
}
span{
  font-size: 1em;
  font-weight: bold;
  color: #dc3545;
}
.paragraf{
  margin-top:10px;
  font-size: 1em;

  font-weight: 100;
}

</style>

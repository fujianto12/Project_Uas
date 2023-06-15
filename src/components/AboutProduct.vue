<template>
  <div class="about-product p-5">
    <div class="container">
      <div class="row border border-danger p-3">
        <div class="col-md-6 col-sm-12 border border-success shadow">
          <img
            src="../assets/peter-john-manlapig-YFsZMJs_46E-unsplash.jpg"
            class="rounded-circle aboutImg col-sm-12 "
            width="400"
          />
        </div>
        <div class="col-md-6 col-sm-12 p-4">
          <div class="container">
            <h1 class="shadow text-center">About Product</h1>
            <p class="shadow p-4">
              pengguna dapat diuntungkan dengan menggunakan produk tersebut.
              Manfaat ini bisa berupa solusi untuk masalah atau kebutuhan
              tertentu, efisiensi atau peningkatan kinerja, penghematan waktu
              atau uang, atau pengalaman pengguna yang lebih baik. Anda dapat
              mencantumkan testimonial pelanggan atau ulasan positif tentang
              produk tersebut. Ini dapat membantu membangun kepercayaan calon
              pelanggan dan menunjukkan keandalan atau keunggulan produk.
            </p>
          </div>
          <router-link to="/products" class="btn buttonShop mt-3"
            >See Products</router-link
          >
        </div>
      </div>
    </div>
  </div>
  <hr />
</template>

<script>
export default {
  name: "AboutProduct",
};
</script>

<style>
.buttonShop {
  background-image: url(../assets/button.png);
  background-color: transparent;
  border: none;
  text-decoration: none;
  color: black;
  padding: 14px 80px 14px 75px;
  transition: 0.3s all ease-in-out;
}
.buttonShop:hover {
  transform: scale(0.91);
  font-weight: bold;
  font-style: italic;

}


</style>

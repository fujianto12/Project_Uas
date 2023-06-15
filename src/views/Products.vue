<template>
  <div class="products">
    <div class="container">
      <div class="row">
        <div class="col mt-4">
          <h2>Daftar <strong>Products</strong></h2>
        </div>
      </div>

      <!-- Search  -->
      <div class="row mt-3">
        <div class="col">
          <div class="input-group mb-3">
            <div class="form-floating">
              <input
                v-model="search"
                type="text"
                class="form-control"
                id="floatingInputGroup1"
                placeholder="Cari"
                @keyup="searchProduct"
              />
              <label for="floatingInputGroup1"
                >Cari Barang Kesukaan Anda..</label
              >
            </div>
            <span class="input-group-text">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                fill="currentColor"
                class="bi bi-search"
                viewBox="0 0 16 16"
              >
                <path
                  d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"
                />
              </svg>
            </span>
          </div>
        </div>
      </div>

      <div class="row">
        <div
          class="col-lg-3 col-md-6"
          v-for="product in products"
          :key="product.id"
        >
          <div class="card border border-danger shadow mt-5" style="width: 18rem">
            <img :src="product.image" class="card-img-top" style="" />
            <div class="card-body">
              <h5 class="card-title">{{ product.name }}</h5>
              <router-link class="btn btn-success" :to="'/products/' + product._id"
                >See Detail
                </router-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <Footers />
</template>

<script>
import axios from "axios";
import Footers from "../components/Footers.vue";
export default {
  components: {
    Footers,
  },
  data() {
    return {
      products: [],
      search: "",
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    },
    searchProduct() {
      axios
        .get("https://uas-pw1-if2c-1.vercel.app/products?q=" + this.search)
        .then((response) => this.setProducts(response.data))
        .catch((error) => console.log(error));
    },
  },
  mounted() {
    axios
      .get("https://uas-pw1-if2c-1.vercel.app/products")
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style></style>

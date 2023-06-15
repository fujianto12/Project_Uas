<template>
  <div class="container">
    <div class="row mt-5">
      <div class="col">
        <nav aria-label="breadcrumb">
          <ol class="breadcrumb">
            <li class="breadcrumb-item">
              <router-link to="/" class="text-dark">Home</router-link>
            </li>
            <li class="breadcrumb-item">
              <router-link to="/products" class="text-dark"
                >Product</router-link
              >
            </li>
            <li class="breadcrumb-item active" aria-current="page">
              Product Detail
            </li>
          </ol>
        </nav>
      </div>
    </div>

    <div class="card mb-3 shadow">
      <div class="row g-0">
        <div class="col-md-4">
          <img :src="product.image" class="img-fluid rounded-start" alt="..." />
        </div>
        <div class="col-md-8">
          <div class="card-body">
            <h5 class="card-title">Nama Barang:</h5>
            <p>{{ product.name }}</p>
            <hr />
            <p>
              Jumlah Sisa : <b>{{ product.quantity }}</b>
            </p>
            <p>
              Harga: Rp. <b> {{ product.price }}</b>
            </p>

            <hr>
            <div
              class="accordion accordion-flush mt-5"
              id="accordionFlushExample"
            >
              <div class="accordion-item">
                <h2 class="accordion-header">
                  <button
                    class="accordion-button collapsed"
                    type="button"
                    data-bs-toggle="collapse"
                    data-bs-target="#flush-collapseOne"
                    aria-expanded="false"
                    aria-controls="flush-collapseOne"
                  >
                    Lihat Deskripsi
                  </button>
                </h2>
                <div
                  id="flush-collapseOne"
                  class="accordion-collapse collapse"
                  data-bs-parent="#accordionFlushExample"
                >
                  <div class="accordion-body">
                    {{ product.description }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- review -->
    <div class="container">
      <div class="accordion mt-5" id="accordionExample">
        <div class="accordion-item">
          <h2 class="accordion-header">
            <button
              class="accordion-button"
              type="button"
              data-bs-toggle="collapse"
              data-bs-target="#collapseOne"
              aria-expanded="true"
              aria-controls="collapseOne"
            >
              Review

              <!-- star full -->
              <i class="bi bi-star-fill"></i>
              <i class="bi bi-star-fill"></i>
              <i class="bi bi-star-fill"></i>
              <!-- star setengah -->
              <i class="bi bi-star-half"></i>
              <!-- star kosong -->
              <i class="bi bi-star"></i>
              
            </button>
          </h2>
          <div
            id="collapseOne"
            class="accordion-collapse collapse show"
            data-bs-parent="#accordionExample"
          >
            <div class="accordion-body" v-for="review in reviews" :key="review">
              <div class="card mb-3" style="max-width: 520px">
                <div class="row">
                  <div class="col-md-6 col-lg-6">
                    <img :src="review.image" class="img-fluid rounded-start" />
                  </div>
                  <div class="col-md-8">
                    <div class="card-body">
                      <h2 class="card-title">{{ review.name }}</h2>
                      
                      <p class="card-text">
                        {{ review.comment }}
                      </p>
                      <h5 class="card-title">{{ review.country }}</h5>

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
  <br />
  <hr />
  <Footers />
</template>

<script>
import axios from "axios";
import Footers from "../components/Footers.vue";
export default {
  name: "ProductDetail",
  components: {
    Footers,
  },
  data() {
    return {
      product: {},
      reviews: [],
    };
  },
  methods: {
    setProduct(data) {
      this.product = data;
    },
    setReview(dataReview) {
      this.reviews = dataReview;
    },
  },
  mounted() {
    axios
      .get(
        "https://uas-pw1-if2c-1.vercel.app/products/" + this.$route.params.id
      )
      .then((response) => {
        this.setProduct(response.data);
      })
      .catch((error) => {
        console.log(error);
      });

    axios
      .get("https://uas-pw1-if2c-1.vercel.app/productReview/" + this.$route.params.id)
      .then((response) => {
        this.setReview(response.data);
      })
      .catch((error) => console.log(error));
   },
};
</script>

<style>
hr {
  color: red;
}
</style>

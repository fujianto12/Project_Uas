<template>

<div class="shadow p-1 bg-body-tertiary rounded ">
    <nav class="navbar navbar-expand-lg bg-body-tertiary ">
      <div class="container-fluid ">
        <a class="navbar-brand" href="#">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="30"
            height="25"
            fill="currentColor"
            class="bi bi-bag-heart-fill"
            viewBox="0 0 16 16"
            color="red"
          >
            <path
              d="M11.5 4v-.5a3.5 3.5 0 1 0-7 0V4H1v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V4h-3.5ZM8 1a2.5 2.5 0 0 1 2.5 2.5V4h-5v-.5A2.5 2.5 0 0 1 8 1Zm0 6.993c1.664-1.711 5.825 1.283 0 5.132-5.825-3.85-1.664-6.843 0-5.132Z"
            />
          </svg>
          <b style="position: absolute; top: 15px">GoShop</b>
        </a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav" style="margin-left: auto">
            <li class="nav-item">
                <RouterLink class="nav-link" to="/">Home</RouterLink>
            </li>
            <li class="nav-item">
                <RouterLink class="nav-link" to="/products">Products</RouterLink>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>


</template>

<script>
export default {

}
</script>

<style>

</style>
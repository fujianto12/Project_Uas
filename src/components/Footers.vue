<template>
  <footer>
    <div class="social">
      <a href=""><i class="bi bi-instagram"></i></a>
      <a href=""><i class="bi bi-whatsapp"></i></a>
      <a href=""><i class="bi bi-facebook"></i></a>
      <a href=""><i class="bi bi-twitter"></i></a>
    </div>
    <ul class="lis">
      <li>
        <router-link to="/">Home</router-link>
      </li>
      <li>
        <router-link to="/products">Product</router-link>
      </li>
      <li>
        <a href="#">Privacy Policy</a>
      </li>
    </ul>
    <p class="copyright">
        2023 &copy; Pemrograman Web 1
    </p>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style>
footer {
  padding-top:100px;
  background-color: #fff;
}
footer .social {
  text-align: center;
  padding-bottom: 25px;
  color: #4b4c4d;
}

footer .social a {
  font-size: 24px;
  color: inherit;
  border: 1px solid #ccc;
  width: 40px;
  height: 40px;
  line-height: 38px;
  display: inline-block;
  text-align: center;
  border-radius: 50%;
  margin: 0 8px;
  opacity: 0.75;
}
footer .social a:hover {
  opacity: 1;
}

footer ul{
  margin-top: 0;
  padding: 0;
  list-style: none;
  font-size: 18px;
  line-height: 1.6;
  margin-bottom: 0;
  text-align: center;
}
footer ul li{
  display: inline-block;
  padding: 0 15px;
}
footer ul li a{
  color: inherit;
  text-decoration: none;
  opacity: 0.8;
}
footer ul li a:hover{
  opacity: 1;
}

footer .copyright{
  margin-top: 15px;
  text-align: center;
  font-size: 13px;
  color: #aaa;
}

</style>

<template>
  <div id="app">
    <div id="fixed-button-section">
      <div v-for="bms in this.$store.state.mediaSosial" :key="bms.id" :class="`fixed-${bms.name} heartbeat`">
        <a
          :href="`${bms.url}${bms.username}`"
          target="__blank"
          rel="noopener noreferrer"
          :class="`btn-${bms.name}`"
        >
          <img :src="`data:image/png;base64,${bms.image}`" />
        </a>
      </div>
    </div>
    <Navbar />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar";
import Footer from "@/components/Footer";

export default {
  name: "App",
  components: {
    Navbar,
    Footer,
  },
  created() {
    this.$store.dispatch('fetchMediaSosial')
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap");

/* ? ==========Global============================ */
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.heartbeat {
	-webkit-animation: heartbeat 1.5s ease-in-out infinite both;
	        animation: heartbeat 1.5s ease-in-out infinite both;
}

/* ----------------------------------------------
 * Generated by Animista on 2021-6-27 16:38:28
 * Licensed under FreeBSD License.
 * See http://animista.net/license for more info. 
 * w: http://animista.net, t: @cssanimista
 * ---------------------------------------------- */

/**
 * ----------------------------------------
 * animation heartbeat
 * ----------------------------------------
 */
@-webkit-keyframes heartbeat {
  from {
    -webkit-transform: scale(1);
            transform: scale(1);
    -webkit-transform-origin: center center;
            transform-origin: center center;
    -webkit-animation-timing-function: ease-out;
            animation-timing-function: ease-out;
  }
  10% {
    -webkit-transform: scale(0.91);
            transform: scale(0.91);
    -webkit-animation-timing-function: ease-in;
            animation-timing-function: ease-in;
  }
  17% {
    -webkit-transform: scale(0.98);
            transform: scale(0.98);
    -webkit-animation-timing-function: ease-out;
            animation-timing-function: ease-out;
  }
  33% {
    -webkit-transform: scale(0.87);
            transform: scale(0.87);
    -webkit-animation-timing-function: ease-in;
            animation-timing-function: ease-in;
  }
  45% {
    -webkit-transform: scale(1);
            transform: scale(1);
    -webkit-animation-timing-function: ease-out;
            animation-timing-function: ease-out;
  }
}
@keyframes heartbeat {
  from {
    -webkit-transform: scale(1);
            transform: scale(1);
    -webkit-transform-origin: center center;
            transform-origin: center center;
    -webkit-animation-timing-function: ease-out;
            animation-timing-function: ease-out;
  }
  10% {
    -webkit-transform: scale(0.91);
            transform: scale(0.91);
    -webkit-animation-timing-function: ease-in;
            animation-timing-function: ease-in;
  }
  17% {
    -webkit-transform: scale(0.98);
            transform: scale(0.98);
    -webkit-animation-timing-function: ease-out;
            animation-timing-function: ease-out;
  }
  33% {
    -webkit-transform: scale(0.87);
            transform: scale(0.87);
    -webkit-animation-timing-function: ease-in;
            animation-timing-function: ease-in;
  }
  45% {
    -webkit-transform: scale(1);
            transform: scale(1);
    -webkit-animation-timing-function: ease-out;
            animation-timing-function: ease-out;
  }
}


h1,
h2,
h3,
h4,
.salam {
  font-family: "Fredoka One", cursive;
}

strong {
  color: #82a116;
  font-weight: 700;
}
/* ? ==========End Global======================== */

/* ? ==========Fixed Button====================== */
.fixed-whatsapp,
.fixed-instagram,
.fixed-facebook {
  position: fixed;
  bottom: 20px;
  left: 10px;
  z-index: 10;
  background: rgba(250, 249, 247, 0.8);
  height: 40px;
  width: 40px;
  border: 0;
  border-radius: 100%;
  box-shadow: 3px 3px rgba(10, 10, 10, 0.3);
  margin: auto;
}

.fixed-instagram {
  bottom: 80px !important;
}

.fixed-facebook {
  bottom: 140px !important;
}

.fixed-whatsapp .btn-whatsapp,
.fixed-instagram .btn-instagram,
.fixed-facebook .btn-facebook {
  padding: 0;
  width: 100%;
  height: 100%;
}

.fixed-whatsapp .btn-whatsapp:hover,
.fixed-instagram .btn-instagram:hover,
.fixed-facebook .btn-facebook:hover {
  opacity: 0.5;
}

.fixed-whatsapp .btn-whatsapp img,
.fixed-instagram .btn-instagram img,
.fixed-facebook .btn-facebook img {
  width: 100%;
  height: 100%;
  margin: auto;
  padding: 5px;
}
/* ? ==========End Fixed Button================== */

/* ? ==========Navbar============================ */
nav {
  height: 10vh;
}

.navbar .container {
  width: 100%;
}

.navbar img {
  width: 80px;
}

.nav-item {
  font-family: "Fredoka One", cursive;
  border-bottom: 1px #faf9f7 solid;
}

.nav-item:hover {
  color: #e4b569;
}

.nav-item:last-child {
  border-bottom: 0 !important;
}

.navbar-light .navbar-nav .nav-link,
.navbar-light .navbar-nav .nav-link.active {
  color: #333;
}

.navbar-light .navbar-nav .nav-link.active {
  border-left: 0.25rem solid #82a116;
}

.navbar-nav .nav-link {
  padding-left: 1rem;
}

.navbar-collapse {
  width: 100px;
  padding-top: 1rem;
  background: #faf9f7;
  position: relative;
  z-index: 3;
}
/* ? ==========End Navbar======================== */

/* ? ==========Landing Page Section============== */
#landing {
  height: 70vh;
  width: 100%;
  position: relative;
  background: url("https://source.unsplash.com/MGUmEYvGNUU") no-repeat center
    center/cover;
}

#landing::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  background: rgba(240, 240, 240, 0.5);
}

#landing .showcase {
  position: relative;
  z-index: 1;
  background-color: rgba(240, 240, 240, 0.9);
  width: 90%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 2rem 1.5rem;
}

#landing .showcase .salam {
  font-size: 1.2rem;
}

#landing .showcase h1 {
  font-size: 2rem;
}

#landing .showcase p {
  font-size: 1rem;
  font-weight: 400;
}

#landing .showcase a {
  background: #82a116;
  color: #333;
  font-weight: 700;
}
/* ? ==========End Landing Page Section========== */

/* ? =========Tentang Kami Section=============== */
#tentang-kami {
  position: relative;
  background: #e2cfa2;
}

#tentang-kami .showcase {
  margin: 0 auto;
  width: 90%;
  padding: 1rem 1.5rem 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

#tentang-kami h2 {
  margin: 0;
  font-size: 1.7rem;
  text-align: center;
  padding: 2rem 0 1rem;
  text-align: center;
}

#tentang-kami .showcase .section-text {
  order: 3;
}

#tentang-kami .showcase .section-text h3 {
  margin: 0;
  font-size: 1.3rem;
  color: #82a116;
  padding: 2rem 0 1rem;
}

#tentang-kami .showcase .section-text p {
  text-align: justify;
  font-size: 1rem;
  font-weight: 400;
}

#tentang-kami .showcase .section-text p i {
  color: rgb(250, 0, 0);
}

#tentang-kami .showcase .section-image {
  position: relative;
  order: 2;
  width: 100%;
}

#tentang-kami .showcase .section-image img {
  width: 100%;
}

/* ? =========End Tentang Kami Section=========== */

/* ? =========Produk Section===================== */
#produk {
  position: relative;
  background: #faf9f7;
}

#produk .showcase {
  width: 90%;
  margin: 0 auto;
  padding: 1rem 1.5rem 1rem;
}

#produk .showcase h2 {
  margin: 0;
  font-size: 1.7rem;
  text-align: center;
  padding: 1rem 0 1.5rem;
}

#produk .showcase h3 {
  margin: 0;
  font-size: 1.3rem;
  color: #82a116;
  padding: 1rem 0;
}

#produk .showcase h4 {
  margin: 0;
  font-size: 1.1rem;
  color: #333;
  padding: 1rem 0;
}

#produk .showcase p {
  font-size: 1rem;
  font-weight: 400;
}

#produk .showcase .daftar-harga .paket-qurban .col-md-6:nth-child(odd) .card {
  background: #e4e5d5;
}

#produk .showcase .card {
  background-color: #e2cfa2;
  border-radius: 5px;
  border: 0;
  box-shadow: 5px 5px rgba(10, 10, 10, 0.1);
}

#produk .showcase .card-title {
  font-family: "Fredoka One", cursive;
  font-size: 1rem;
}

#produk .showcase .card-subtitle {
  font-size: 0.8rem;
  font-weight: 400;
}

#produk .showcase .card-text {
  text-align: justify;
  font-size: 0.8rem;
  font-weight: 400;
  line-height: 1.3;
}

#produk .showcase .card-text strong {
  color: #333;
  font-size: 0.8rem;
}

#produk .showcase .mengapa-memilih-kami .items {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: stretch;
  grid-gap: 0.5rem;
}

#produk .showcase .mengapa-memilih-kami .items .item {
  text-align: center;
  padding: 1rem;
  background: #e2cfa2;
  border-radius: 5px;
  border: 0;
  box-shadow: 5px 5px rgb(10 10 10 / 10%);
}

#produk .showcase .mengapa-memilih-kami .items p {
  margin: 0;
  padding: 0.3rem 0;
}

#produk .showcase .mengapa-memilih-kami .items .item .title-item {
  font-family: "Fredoka One", cursive;
  font-size: 1rem;
}

#produk .showcase .mengapa-memilih-kami .items .item .title-desc {
  font-size: 0.9rem;
}
/* ? =========End Produk Section================= */

/* ? =========Testimoni Section================= */
#testimoni {
  position: relative;
  background: url("./assets/palembang.jpg") no-repeat center center/cover;
}

#testimoni::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  z-index: 2;
  background: rgba(20, 20, 20, 0.7);
}

#testimoni .showcase {
  position: relative;
  z-index: 3;
  width: 90%;
  margin: 0 auto;
  padding: 1rem 1.5rem 2rem;
}

#testimoni .showcase h2 {
  color: #faf9f7;
  padding: 2rem 0 1rem;
  text-align: center;
  font-size: 1.7rem;
}

#testimoni .showcase p {
  color: #faf9f7;
  font-weight: 400;
  text-align: justify;
  font-size: 1rem;
  padding: 0.5rem 0 1rem;
}

#testimoni .showcase p i {
  color: #fffb14;
}

#testimoni .showcase .card {
  background: rgba(250, 249, 247, 0.8);
}

#testimoni .showcase .card img {
  border-radius: 50%;
  width: 50%;
  margin: 0 auto;
  padding: 1rem 0 1rem;
}
#testimoni .showcase .card .card-body {
  padding: 0 1rem 1rem;
}

#testimoni .showcase .card .card-body p.testimoni-title {
  margin: 0;
  text-align: center;
  color: #333;
  font-family: "Fredoka One", cursive;
  font-size: 1rem;
  padding: 0.5rem 0;
}

#testimoni .showcase .card .card-body p.testimoni-text {
  margin: 0;
  text-align: center;
  color: #333;
  font-weight: 400;
  font-style: italic;
  font-size: 0.8rem;
  line-height: 1.2;
  padding: 0 0.8 0.5rem;
  min-height: 6rem;
}

#testimoni .showcase .card .card-body .rating {
  padding: 0 1rem 0.5rem;
  margin: 0 auto;
  text-align: center;
}
/* ? =========End Testimoni Section================= */

/* ? =========Tablet Devices======================== */
@media (min-height: 768px) {
  .fixed-whatsapp,
  .fixed-instagram,
  .fixed-facebook {
    width: 60px;
    height: 60px;
  }

  .fixed-instagram {
    bottom: 100px !important;
  }

  .fixed-facebook {
    bottom: 180px !important;
  }

  #landing .showcase,
  #tentang-kami .showcase,
  #produk .showcase,
  #testimoni .showcase {
    width: 70%;
  }

  #produk .showcase .card {
    min-height: 10rem;
  }

  #testimoni #testimoni-carousel {
    width: 70%;
    margin: auto;
  }

  #produk .showcase .daftar-harga .paket-qurban .col-md-6:nth-child(odd) .card {
    background: #e2cfa2;
  }

  #produk
    .showcase
    .daftar-harga
    .paket-qurban
    .col-md-6:nth-child(4n + 0)
    .card,
  #produk
    .showcase
    .daftar-harga
    .paket-qurban
    .col-md-6:nth-child(4n + 1)
    .card {
    background: #e4e5d5;
  }

  #produk .showcase .mengapa-memilih-kami .items {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    justify-content: center;
    align-items: stretch;
    grid-gap: 0.5rem;
  }

  #produk .showcase .mengapa-memilih-kami .items .item:nth-child(even) {
    background: #e4e5d5;
  }
}
/* ? =========End Tablet Devices==================== */

/* ? =========Laptop Devices======================== */
@media (min-width: 1024px) {
  .navbar-light .navbar-nav .nav-link.active {
    border-left: 0;
    border-bottom: 0.25rem solid #82a116;
  }

  #landing {
    height: 90vh;
  }

  #landing .showcase,
  #produk .showcase,
  #testimoni .showcase {
    width: 50%;
  }

  #landing .showcase .salam {
    font-size: 2rem;
  }

  #landing .showcase h1 {
    font-size: 3rem;
  }

  #landing .showcase p {
    font-size: 1.2rem;
  }

  #tentang-kami {
    height: 60vh;
  }

  #tentang-kami h2 {
    font-size: 2rem;
  }

  #tentang-kami .showcase {
    position: absolute;
    height: 100%;
    width: 50%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    flex-direction: row;
    grid-gap: 2rem;
    justify-content: stretch;
    align-items: center;
    padding: 0 0 2rem;
  }

  #tentang-kami .showcase .section-text {
    order: 1;
  }
  
  #tentang-kami .showcase .section-text {
    order: 2;
  }

  #tentang-kami .showcase .section-text h3 {
    font-size: 1.75rem;
  }

  #tentang-kami .showcase .section-text p {
    font-size: 1.3rem;
  }

  #produk .showcase {
    padding: 1rem 0 2.5rem;
  }

  #produk .showcase h2 {
    font-size: 2rem;
  }

  #produk .showcase h3 {
    font-size: 1.7rem;
  }

  #produk .showcase h4 {
    font-size: 1.4rem;
  }

  #produk .showcase p {
    font-size: 1.3rem;
  }

  #produk .showcase #carouselExampleControls {
    padding: 1rem 7rem;
  }

  #produk .showcase .card {
    min-height: 12rem;
  }

  #produk .showcase .card-title {
    font-size: 1.3rem;
  }

  #produk .showcase .card-subtitle {
    font-size: 1.15rem;
  }

  #produk .showcase .card-text {
    font-size: 1rem;
  }

  #produk .showcase .card-text strong {
    font-size: 1rem;
  }

  #produk
    .showcase
    .daftar-harga
    .paket-qurban
    .col-md-6:nth-child(4n + 0)
    .card,
  #produk
    .showcase
    .daftar-harga
    .paket-qurban
    .col-md-6:nth-child(4n + 1)
    .card {
    background: #e2cfa2;
  }

  #produk
    .showcase
    .daftar-harga
    .paket-qurban
    .col-md-6:nth-child(even)
    .card {
    background: #e4e5d5;
  }

  #testimoni .showcase h2 {
    font-size: 2rem;
  }

  #testimoni .showcase p {
    font-size: 1.2rem;
  }

  #testimoni #testimoni-carousel {
    width: 40%;
  }
}
/* ? =========End Laptop Devices==================== */
</style>

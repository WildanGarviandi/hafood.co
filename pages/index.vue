<template>
  <section class="root">
    <section class="top-container">
      <h1 class="title-top-container"> Kami menyajikan menu menu pilihan dari berbagai katering untuk anda </h1>
      <h2 class="sub-title-top-container">Pilihan paket mulai dari harian, mingguan, hingga bulanan dengan pelayanan dan rasa yang maksimal</h2>
    </section>
    <section class="content">
      <span class="desc-carousel">Di buat secara fresh dan langsung di kirim sesuai jadwal yang ada pesan</span>
      <v-carousel class="carousel-gallery-food">
        <v-carousel-item v-for="(item,i) in imagePackage" :src="item.src" :key="i"></v-carousel-item>
      </v-carousel>
    </section>
    <section class="content">
      <v-carousel class="carousel-gallery-food">
        <v-carousel-item v-for="(item,i) in imageSchedule" :src="item.src" :key="i"></v-carousel-item>
      </v-carousel>
      <span class="desc-carousel">Dengan partner katering terpercaya, kami jamin pelayanan kami paling baik</span>
    </section>
    <section class="section-option-route">
      <h2 class="title-section-option-route">Siap untuk order? atau anda ingin update produk anda?</h2>
      <v-layout row wrap>
       <v-flex xs12 sm2 offset-sm3>
         <nuxt-link :to="{ name: 'client', params: {  }}">
            <v-card>
              <v-card-media src="/img/customer-section.jpg" height="200px">
              </v-card-media>
              <v-card-title primary-title>
                <div>
                  <h3 class="headline mb-0">Siap untuk order?</h3>
                  <div>Order? silakan login dan pesan disini <br>cek, dan personalisasi pesanan mu</div>
                </div>
              </v-card-title>
            </v-card>
         </nuxt-link>
      </v-flex>
      <v-flex xs12 sm2 offset-sm2>
        <nuxt-link :to="{ name: 'partner', params: {  }}">
          <v-card>
            <v-card-media src="/img/merchant-section.jpg" height="200px">
            </v-card-media>
            <v-card-title primary-title>
              <div>
                <h3 class="headline mb-0">Punya produk baru?</h3>
                <div>Perbarui dan kelola produk mu disini<br>kelola produk katering milik anda</div>
              </div>
            </v-card-title>
          </v-card>
        </nuxt-link>
      </v-flex>
      </v-layout>
    </section>
  </section>
  <!-- <ul class="users">
      <li v-for="(user, index) in users" :key="index" class="user">
        <nuxt-link :to="{ name: 'partner', params: { id: index }}">
          {{ user.name }}
        </nuxt-link>
      </li>
    </ul> -->
</template>


<script>
import axios from "~/plugins/axios";

export default {
  async asyncData() {
    let { data } = await axios.get("/api/users");
    return { users: data };
  },
  head() {
    return {
      title: "Hafood.co"
    };
  },
  data() {
    return {
      imagePackage: [
        {
          src: "/img/slide-food/slide1.jpg"
        },
        {
          src: "/img/slide-food/slide2.jpg"
        },
        {
          src: "/img/slide-food/slide3.jpg"
        },
        {
          src: "/img/slide-food/slide4.jpg"
        }
      ],
      imageSchedule: [
        {
          src: "/img/slide-schedule/slide1.jpg"
        },
        {
          src: "/img/slide-schedule/slide2.jpg"
        },
        {
          src: "/img/slide-schedule/slide3.jpg"
        },
        {
          src: "/img/slide-schedule/slide4.jpg"
        }
      ]
    };
  }
};
</script>

<style scoped>
.top-container {
  background-image: url("~assets/img/background-main.jpg");
  background-size: cover; /* <------ */
  background-repeat: no-repeat;
  background-position: center center;
  padding: 300px 0 300px 0;
}

.title {
  margin: 30px 0;
}
.users {
  list-style: none;
  margin: 0;
  padding: 0;
}
.user {
  margin: 10px 0;
}

a {
  color: #FFFFFF;
    text-decoration: none;
}

ul {
  list-style-type: none;
  margin: 0;
  padding-right: 200px;
  overflow: hidden;
  background-color: #333333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 26px 26px 26px 26px;
  text-decoration: none;
}

li a:hover {
  background-color: #111111;
}

.title-top-container {
  color: azure;
  font-weight: 200;
  font-size: 3em;
  padding: 0 80px 0 80px;
}

.sub-title-top-container {
  color: rgb(224, 224, 224);
  font-weight: 100;
  font-size: 20px;
  padding: 0 100px 0 100px;
}
.img-icon-small-top {
  margin-top: 8px;
  width: 56px;
  position: absolute;
  height: 56px;
}

.carousel-gallery-food {
  margin: 0px 0px 0px 0px;
}

.desc-carousel {
  font-size: 30px;
  font-weight: 100;
  margin: 80px 0px 0px 0px;
}

.section-option-route {
  background-image: url("~assets/img/background-main-bottom.jpg");
  background-size: cover; /* <------ */
  background-repeat: no-repeat;
  background-position: center center;
  padding: 60px 0 60px 0;
}

.title-section-option-route {
  color: white;
  font-size: 2em;
  margin: 0px 0px 30px 0px;
}
</style>

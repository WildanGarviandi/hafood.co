<template>
  <section class="root">
    <section class="navigation">
      <img src="~assets/img/hafood-icon-small.png" class="img-icon-small-top"/>
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="#news">Partner</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><a href="#about">About</a></li>
      </ul>
    </section>
    <section class="content">
      <v-layout>
        <v-flex xs18 sm12 offset-sm0>
          <v-card>
            <v-container fluid>
              <v-layout row wrap>
                <v-flex
                  v-for="n in 13"
                  :key="n" 
                  sm2 offset-sm0
                >
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
        </v-container>
      </v-card>
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
  color: #ffffff;
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

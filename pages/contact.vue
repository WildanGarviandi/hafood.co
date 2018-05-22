<template>
  <section class="root">
    <section class="top-container">
        <h1 class="title-top-container">Dari anda untuk anda, Produk terbaik dengan kualitas yang kami jaga dan kelola</h1>
      <!-- <h1 class="title-top-container"> Kami menyajikan menu menu pilihan dari berbagai katering untuk anda </h1>
      <h2 class="sub-title-top-container">Pilihan paket mulai dari harian, mingguan, hingga bulanan dengan pelayanan dan rasa yang maksimal</h2> -->
    </section>
    <section class="container">
      <h2>Kami sebuah lembaga yang menemukan masalah dengan adanya tidak berkembang nya dunia katering yang mahsyur</h2><br/>
      <p>Pertama ide ini muncul karena kami merasa penggiat katering telah ketinggalan zaman nya dan sulit bersaing dengan pasar modern yang ada.</p>
      <p>semoga dengan adanya Hafood.co yang memfalisitasi penggiat katering bisnis katering yang ada ini akan maju dan berguna.</p>
    </section>
  </section>
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
  }
};
</script>

<style scoped>
.top-container {
  background-image: url("~assets/img/background-main.jpg");
  background-size: cover; /* <------ */
  background-repeat: no-repeat;
  background-position: center center;
  padding: 200px 0 200px 0;
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
</style>

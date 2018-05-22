<template>
  <v-app>
    <v-toolbar dark color="dark-grey">
      <img src="~assets/img/hafood-icon-small.png" class="img-icon-small-top"/>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn flat href="/">Home</v-btn>
        <v-btn flat href="">Partner</v-btn>
        <v-btn flat href="/contact">Contact</v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <nuxt/>
    <my-footer/>
</v-app>
</template>

<script>
import MyFooter from "~/components/Footer.vue";

export default {
  components: {
    MyFooter
  }
};
</script>

<style>
.root {
  text-align: center;
}

.button,
.button:visited {
  display: inline-block;
  color: black;
  letter-spacing: 1px;
  background-color: #fff;
  border: 2px solid #000;
  text-decoration: none;
  text-transform: uppercase;
  padding: 15px 45px;
}

.button:hover,
.button:focus {
  color: #fff;
  background-color: #000;
}

.title {
  color: #000;
  font-weight: 300;
  font-size: 2.5em;
  margin: 0;
}
.img-icon-small-top {
  margin-top: 0px;
  width: 56px;
  position: absolute;
  height: 56px;
}
</style>

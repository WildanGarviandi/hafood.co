<template>
  <section class="root">
    <section class="content" v-if="false">
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
                        <h3 class="headline mb-0">sdf {{ users }} </h3>
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
    <section class="content" v-else>
      
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
      response: {},
      user: {
        email: '',
        password: ''
      },
      userRegister: {
        email: '',
        fullname: '',
        password: ''
      },
      passwordRules: [
        (v) => !!v || 'Password is required',
        (v) => v.length >= 5 || 'Password must be 5 or more than 5 characters'
      ],
      valid: false,
      emailRules: [
        (v) => !!v || 'E-mail is required',
        (v) => /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
      ]
    }
  },
  methods: {
    async handleSubmitLogin() {
      console.log("called ", this.user)
      let { data } = await axios.post('http://localhost:1323/user/client/login', this.user)
      return { response: data }
    },
    async handleSubmitRegister() {
      console.log()
      let { data } = await axios.post('http://localhost:1323/user/client/register', this.userRegister)
      return { response: data }
    }
  }
};
</script>

<style scoped>
.form-login {
  padding: 100px;
}

.title-form {
  color: white;
  padding: 20px;
  font-size: 3em;
}

</style>

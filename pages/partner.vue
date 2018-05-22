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
    <section class="content" v-else>
      <v-layout>
        <v-flex xs12 sm6 offset-sm3>
          <v-card>
            <v-card-media src="/img/slide-food/slide1.jpg" height="300px">
              <h2 class="title-form">Login Merchant</h2>
            </v-card-media>
            <v-form class="form-login" method="post" action="http://localhost:1323/client/login" id="nativeForm" v-model="valid">
              <v-text-field
                label="Email"
                v-model="email"
                :rules="emailRules"
                required
                name="email"
              ></v-text-field>
              <v-text-field
                label="Password"
                v-model="password"
                :rules="passwordRules"
                :counter="5"
                required
                name="password"
              ></v-text-field>

              <v-btn @click="submit" :disabled="!valid">submit</v-btn>
            </v-form>
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
  data () {
    return { 
      password: '',
      passwordRules: [
        (v) => !!v || 'Password is required',
        (v) => v.length > 5 || 'Password must be more than 5 characters'
      ],
      valid: false,
      email: '',
      emailRules: [
        (v) => !!v || 'E-mail is required',
        (v) => /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
      ]
    }
  },
  methods: {
    submit() {
      nativeForm.submit()
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

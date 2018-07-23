<template>
  <v-flex xs12 sm8 md4>
    <v-card class="elevation-3">
      <v-toolbar color="primary">
        <v-toolbar-title>Dashboard</v-toolbar-title>
      </v-toolbar>
      <v-card-text>
          <div v-if="userExists">Welcome {{ pseudo }}.</div>
          <div v-else>{{ msg }}</div>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn v-if="userExists" color="alert" @click="destroyAccount">Destroy Account</v-btn>
        <v-btn v-else color="primary" to="/signup">Sign up</v-btn>
      </v-card-actions>
    </v-card>
  </v-flex>
</template>

<script>
import Users from '@/js/users'

export default {
  name: 'dashboard',
  data () {
    return {
      msg: 'Welcome to your truffle-Vuetify DAPP',
      pseudo: undefined
    }
  },
  computed: {
    userExists: function () {
      console.log(this.pseudo)
      return (typeof this.pseudo !== 'undefined')
    }
  },
  beforeCreate: function () {
    Users.init().then(() => {
      Users.exists(window.web3.eth.accounts[0]).then((exists) => {
        if (exists) {
          Users.authenticate().then(pseudo => {
            this.pseudo = pseudo
          })
        }
      })
    }).catch(err => {
      console.log(err)
    })
  },
  methods: {
    destroyAccount: function (e) {
      e.preventDefault()
      Users.destroy().then(() => {
        this.pseudo = undefined
      }).catch(err => {
        console.log(err)
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
  display: block;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

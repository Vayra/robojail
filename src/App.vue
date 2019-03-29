/* eslint-disable */

<template>
  <div id="app">
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
      integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T"
      crossorigin="anonymous"
    >
    <h1>Robot jail</h1>
    <img alt="Vue logo" src="./assets/jail.png">
    <!--<HelloWorld msg="FAKEJson fun times"/>-->
    <div class="row">
      <div class="col" v-for="criminal in criminals" v-bind:key="criminal.id">
        <convictCard
          :id="criminal.id"
          :name="criminal.givenName + ' ' + criminal.familyName"
          :crime="criminal.crime"
          :headshot="criminal.headshot"
        />
      </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import convictCard from "./components/convictCard.vue";
import data from "./assets/data.json";

//const axios = require('axios')

export default {
  name: "app",
  components: {
    HelloWorld,
    convictCard
  },
  data() {
    return {
      criminals: null
    };
  },
  created() {
    this.getData();
  },
  methods: {
    async getData() {
      /*
      let criminals;
      let payload = {
        token: "CaKtpLTHh1Fi3Nh-FawIew",
        data: {
          id: "numberInt",
          headshot: "personAvatar",
          givenName: "nameFirst",
          familyName: "nameLast",
          crime: "stringWords|5,8",
           _repeat: 10
        }
      };
      await axios({
        method: "post",
        url: "https://app.fakejson.com/q",
        data: payload
      }).then(function(resp) {
        criminals = resp.data
      });*/
      console.log(data);
      this.criminals = data;
      //console.log(this.criminals)
    }
  }
};
</script>

<style>
body {
  background: #a8a8a8
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}
</style>

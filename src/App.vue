<template>
  <div id="app">
    <Card v-for="item in company" v-bind:key="item.id" v-bind:info="item"/>
  </div>
</template>

<script>
import axios from "axios";
import Card from "./components/Card";

export default {
  name: "App",
  components: {
    Card
  },
  data() {
    return {
      company: []
    };
  },
  mounted() {
    this.getCompanyData();
  },
  methods: {
    async getCompanyData() {
      let company_param = "snap,tsla",
        token = "uojwh6sISmZX6qqbgzuh3jruxQJzKJJP9VxMhunjDIZEqJO770i8vAWtitKw";
      axios
        .get(
          "https://api.worldtradingdata.com/api/v1/stock?symbol=" +
            company_param +
            "&api_token=" +
            token
        )
        .then(res => {
          // handle success
          this.company = res.data.data;
          console.log(this.company);
        })
        .catch(error => {
          // handle error
          console.log(error);
        })
        .finally(() => {
          // always executed
        });
    }
  }
};
</script>

<style>
body {
  background: #fff;
  font: normal 14px Arial, sans-serif;
  color: #121212;
  width: 100%;
  height: 100%;
}
.wrapper,
#app {
  margin: 100px;
  font-size: 0;
}
</style>

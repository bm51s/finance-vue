<template>
  <div id="app">
    <Card />
  </div>
</template>

<script>
import Card from "./components/Card";

export default {
  name: "App",
  components: {
    Card
  },
  methods: {

    async getCompanyData() {
      let company = this.props.company,
      token = "uojwh6sISmZX6qqbgzuh3jruxQJzKJJP9VxMhunjDIZEqJO770i8vAWtitKw";
    axios
      .get(
        "https://api.worldtradingdata.com/api/v1/stock?symbol=" +
          company +
          "&api_token=" +
          token
      )
      .then(res => {
        // handle success
        let response = res.data.data;
        this.setState({ params: response });
        console.log(res);
        console.log(res.data.data[0]);
        console.log(this.state.params);
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
#root {
  margin: 100px;
  font-size: 0;
}
</style>

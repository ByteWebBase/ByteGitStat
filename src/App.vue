<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-app-bar-title>ByteCommitChart</v-app-bar-title>
      </div>

      <v-spacer></v-spacer>

      <v-btn :loading="loading" :disabled="loading" @click="dataInit()" text>
        <span class="mr-2">{{ dataTime }}</span>
        <v-icon>mdi-refresh</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <chart ref="chart" />
    </v-main>
  </v-app>
</template>

<script>
import chart from "./components/chart";
import axios from "axios";

export default {
  name: "App",

  components: {
    chart,
  },

  data: () => ({
    //
    loading: false,
    dataTime: null,
  }),
  methods: {
    async updateData() {
      const baseURL = "https://qcs7l1.fn.thelarkcloud.com/GetCommitData";
      let newData = [];

      try {
        const res = await axios({
          method: "get",
          url: baseURL,
          headers: {},
        });
        newData = res;
        console.log(res.data);
      } catch (error) {
        console.log(error);
      }
      this.$refs.chart.dataList = newData.data;
    },
    dataInit() {
      this.loading = true;
      this.updateData();
      this.dataTime = new Date();
      this.loading = false;
    },
  },
};
</script>

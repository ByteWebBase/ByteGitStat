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
    dataInit() {
      this.loading = true;
      this.dataTime = new Date();
      this.$refs.chart.data = [
        { name: "ByteWebBase", cnt: 233 },
        { name: "ohhhh", cnt: 1234 },
      ];
      this.loading = false;
    },
  },
};
</script>

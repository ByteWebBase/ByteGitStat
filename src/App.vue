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
      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld,
  },

  data: () => ({
    //
    loading: false,
    dataTime: 0,
  }),
  methods: {
    dataInit() {
      this.loading = true;
      this.dataTime = new Date();
      alert("get init data!");
      this.loading = false;
    },
  },
};
</script>

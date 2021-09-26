<template>
  <v-container>
    <v-data-table
      :headers="headers"
      :items="dataList"
      :items-per-page="10"
      class="elevation-1"
      :loading="isLoading"
      loading-text="Loading... Please wait"
    ></v-data-table>
  </v-container>
</template>

<script>
export default {
  name: "chart",
  data: () => ({
    headers: [
      {
        text: "Name",
        align: "start",
        sortable: false,
        value: "name",
      },
      { text: "Commits", value: "cnt" },
    ],
    isLoading: false,
    dataList: [],
  }),
};
</script>

<style>
</style>
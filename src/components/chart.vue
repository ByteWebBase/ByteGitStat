<template>
  <v-container>
    <v-data-table
      :headers="headers"
      :items="data"
      :items-per-page="10"
      class="elevation-1"
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
    data: [],
  }),
};
</script>

<style>
</style>
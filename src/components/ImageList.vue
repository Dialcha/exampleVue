<template>
  <v-container>
    <v-row>
      <v-col>
        <v-card v-for="item in item.hits" v-bind:key="item.id" sm="4" cols="12">
          <img :src="item.previewURL" alt>
          <v-card-title>{{ item.user }}</v-card-title>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "ImageList",
  props: ["items"],
};
</script>
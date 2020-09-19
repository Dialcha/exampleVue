<template>
    <v-container>
        <v-text-field v-model="word" label="Search"></v-text-field>
        <v-btn class="mx-2" fab dark color="indigo"  @click="searchItem">
            <v-icon>mdi-plus</v-icon>
        </v-btn>
    </v-container>
</template>

<script>
import axios from 'axios';
export default {
    name: "Search",
    data: () => ({
        search: [],
        word:'',
  }),
    methods: {
        searchItem(){
            axios
                .get("https://pixabay.com/api/?key=18325849-94cafec8b0f30985ae8cfbdde&q=" + this.word + "&image_type=photo")
                .then((response) => {
                    this.search = response.data,
                    this.$emit("searchResult", response.data);
                })
        }
    }
}
</script>
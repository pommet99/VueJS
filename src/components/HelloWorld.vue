<template>

<v-card
    class="mx-auto"
    max-width="400"
  >
    <v-img
      class="white--text align-end"
      height="200px"
      :src="image"
    >
      <v-card-title>{{title}}</v-card-title>
    </v-img>

    <v-card-subtitle class="pb-0">Number 1</v-card-subtitle>

    <v-card-text class="text--primary">
      <div>{{city}}, {{country}}.</div>
      <b>View More </b>
    </v-card-text>
</v-card>

</template>

<script>
export default {
  name: 'destinations',
  props: {
    image:String,
    title:String,
    city:String,
    country:String,
  },
}

</script>

<style>

</style>

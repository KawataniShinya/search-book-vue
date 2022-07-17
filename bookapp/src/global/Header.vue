<template>
  <div>
    <v-app-bar app color="info" dark>
      <div class="text-h5">Search Books</div>
      <v-spacer></v-spacer>
      <v-btn
        color="warning"
        @click="deleteLocalStrage"
      >削除</v-btn>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    deleteLocalStrage() {
      this.$emit('delete-local-strage');
    }
  }
};
</script>

<style>
</style>
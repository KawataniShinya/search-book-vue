<template>
  <div>
    <v-row>
      <v-col cols="12">
        <div align="center">
          <v-btn color="primary" to="/search">検索</v-btn>
        </div>
      </v-col>
    </v-row>
    <div class="my-10"></div>
    <v-row>
      <v-col cols="12" sm="6" v-for="book in books" :key="book.id">
        <v-card>
          <v-row>
            <v-col cols="4">
              <v-img :src="book.image"></v-img>
            </v-col>
            <v-col cols="8">
              <v-card-title>{{ book.title }}</v-card-title>
              Read Date : {{ book.readDate }}
              <br>
              Personal Note : {{ book.memo }}
              <v-spacer></v-spacer>
              <v-card-actions>
                <v-btn
                  :to="{name: 'BookEdit', params: {id: book.id}}"
                  color="indigo"
                  fab
                  small
                  dark
                >
                  <v-icon>mdi-pencil</v-icon>
                </v-btn>
              </v-card-actions>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  props: {
    books: Array
  }
}
</script>

<style>

</style>
<template>
  <div>
    <v-row>
      <v-col cols="12">
        <v-card class="mx-auto">
          <v-row>
            <v-col cols="4">
              <v-img :src="book.image"></v-img>
            </v-col>
            <v-col cols="8">
              <v-card-title>
                Title : {{ book.title }}
              </v-card-title>
              Read Date :
              Personal Memo :
              <v-textarea solo class="mx-2" v-model="book.memo">
                {{ book.memo }}
              </v-textarea>
              <v-card-actions>
                <v-btn color="secondary" to="/">一覧に戻る</v-btn>
                <v-btn color="info">保存</v-btn>
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
  name: 'BookEdit',
  props: {
    books: Array
  },
  data() {
    return {
      book: ''
    }
  },
  beforeRouteEnter (to, from, next) {
    next(vm => {
      vm.$nextTick(() => {
        vm.book = vm.books[vm.$route.params.id];
        console.log(vm.book);
      })
    })
  }
}
</script>

<style>

</style>
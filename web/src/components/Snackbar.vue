<template>
  <v-snackbar class="snackbar" top :color="color" v-model="show" :timeout="12000">
    {{msg}}
    <v-btn flat color="f3f3f3"  @click.native="show = false">Close</v-btn>
  </v-snackbar>
</template>

<script>
export default {
  computed: {
    show: {
      // getter
      get() {
        return this.$root.$data.store.snack.show;
      },
      // setter
      set: function (show) {
        this.$set(this.$root.$data.store.snack, 'show', show);
      }
    },
    msg(){
      return this.$root.$data.store.snack.msg;
    },
    color(){
      return this.$root.$data.store.snack.color;
    }

  },

}
</script>
<style>
.v-snack__wrapper{
  border-radius: 2px;
}
</style>


<template>
  <div class="text-center ma-2">

    <v-snackbar
      v-model="$store.state.snackbar.show"
    >
      {{ $store.state.snackbar.text }}

      <template v-slot:action="{ attrs }">
        <v-btn
          @click="$store.commit('hideSnackbar')"
          color="pink"
          text
          v-bind="attrs"

        >
          Close
        </v-btn>
      </template>
    </v-snackbar>
  </div>
</template>



<script>
  export default {
    data: () => ({
    }),
  }
</script>


<style lang="sass">
  .v-snack:not(.v-snack-absolute)
    height: 100%
</style>
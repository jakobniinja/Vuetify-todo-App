<template>
<div >

    <v-btn
    @click="$store.commit('toggleSorting')"
    v-if="$store.state.sorting"
    class="button-done-sorting"
    color="deep-purple lighten-2"
    >
        done Sorting
    </v-btn>
</div>
</template>

<script>
export default {

}
</script>

<style lang="sass">
    .button-done-sorting    
        position: fixed
        bottom: 20px
        left: 50%
</style>
<template>
  <div class="home pa-9">
    <list-tasks/>
    <button-done-sorting/>
    


  </div>
</template>



<script>

import ListTasks from '../components/ListTasks.vue';
import ButtonDoneSorting from '../components/ButtonDoneSorting'


export default {
  name: "Todo",

  components:{
    'ListsTasks': ListTasks,
    'button-done-sortin': ButtonDoneSorting,
    ListTasks,
    ButtonDoneSorting
  }
};
</script>

<style lang="sass">
.no-task
  position: absolute
  left: 40%
  top: 50%
  tranform:  translate(-50%, -50%)

</style>

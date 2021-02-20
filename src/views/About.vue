<template>
  <div class="about pa-6">



    <h1>About Me: </h1>
    <List-info/>


  </div>
</template>


<script>

import listinfo from '../components/ListOfInfo'
export default {
  components: {
    'List-info': listinfo
  }
  

}
</script>


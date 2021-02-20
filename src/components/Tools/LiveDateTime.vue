<template>
  <div>
    <div class="text-subtitle-1 ml-4">{{date}} </div>
  </div>
</template>

<script>
import {format} from 'date-fns'


export default {
    data() {
        return{
            date:''
        }
        
    },
    methods: {
        getDate() {
            this.date = format(new Date(), 'MM d, H:mm:ss')
            setTimeout(this.getDate, 1000)
        }

    },
    mounted() {
        this.getDate()
    }
};



</script>

<style scoped>
</style>
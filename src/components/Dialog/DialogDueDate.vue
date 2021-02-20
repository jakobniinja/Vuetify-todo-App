<template>
<div class="">


      <v-dialog
        ref="dialog"
        :value="true"
        :return-value.sync="date"
        color="deep-purple"
        persistent
        width="290px"
      >
        <v-date-picker
          v-model="date"
          scrollable
          color="deep-purple"
        >
          <v-spacer></v-spacer>
          <v-btn
            @click="$emit('close')"

            text
            color="deep-purple"
          >
            Cancel
          </v-btn>
          <v-btn
            @click="saveTask"
            text
            color="deep-purple"
          >
            OK
          </v-btn>
        </v-date-picker>
      </v-dialog>

</div>

</template>

<script>
export default {
    props: ['task'],


    data() {
        return {
            date: null
        }
    },

    methods: {
        saveTask() {
            let payload = {
                id: this.task.id,
                dueDate: this.date
            }
            this.$store.dispatch('updateTaskDueDate', payload)
            this.$emit('close')
        }
    }
    ,
    mounted() {
        if(this.task.dueDate){
            this.date  = this.task.dueDate
        }
    }

}
</script>

<style scoped>
</style>
<template>


    <v-list v-if="$store.state.tasks.length" flat class="pt-0">
              <draggable
        v-model="tasks"
        handle=".handle"

      >
              <task
        v-for="task in tasks" 
        :key="task.id"
        :task="task"
        />
        
    </draggable>


    </v-list>
    <div v-else class="no-task">
        <notask/>
    </div>
</template>

<script>


import Task from '../components/Task'
import NoTask from '../components/NoTask'
import draggable from 'vuedraggable'

export default {
    components:{
        'task' : Task,
        'notask': NoTask,
        draggable
    },

    computed: {
        tasks: {
            get() {
                return this.$store.getters.tasksFiltered
            },
            set(value) {
                this.$store.dispatch('setTasks', value)
            }
        }
    }

}
</script>

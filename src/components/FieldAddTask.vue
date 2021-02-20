<template>
  <v-text-field
    class="field-add-task pa-3"
    @keyup.enter="addTask"
    v-model="newTaskTitle"
    outlined
    label="Add task"
    hide-details
    clearable
  >
    <template v-slot:prepend>
      <v-tooltip bottom>
        I'm a tooltip
      </v-tooltip>
    </template>
    <template v-slot:append>
      <v-icon
        @click="addTask"
        color="deep-purple lighten-2"
        :disabled="newTaskTitleInvalid"
      >
        mdi-plus
      </v-icon>
    </template>
  </v-text-field>
</template>

<script>


export default {

  data() {
    return {
      newTaskTitle: "",
    };
  },
  computed: {
    newTaskTitleInvalid() {
      return !this.newTaskTitle;
    },
  },
  methods: {
    addTask() {
      if (!this.newTaskTitleInvalid) {
        this.$store.dispatch("addTask", this.newTaskTitle);
        this.newTaskTitle = "";
      }
    },
  },
};
</script>


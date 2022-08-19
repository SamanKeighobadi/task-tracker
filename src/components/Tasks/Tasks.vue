<template>
  <div v-for="task in tasks" :key="task.id">
    <Task
      :day="task.day"
      :text="task.text"
      :reminder="task.reminder"
      :id="task.id"
      @delete-task="$emit('delete-task',task.id)"
    />
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: { Task },
  emits:['delete-task']
};
</script>
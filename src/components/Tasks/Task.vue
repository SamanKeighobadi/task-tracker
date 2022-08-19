<template>
  <div class="task">

    <vs-list>
      <vs-alert active="true">
        <vs-list-item :title="text" :subtitle="day">
          <vs-icon @click="deleteTask" icon="clear"></vs-icon>
          <div v-if="reminder">
            <vs-tooltip text="Reminder On">
              <vs-icon icon="notifications_active" color="primary"></vs-icon>
            </vs-tooltip>
          </div>
          <div v-else>
            <vs-tooltip text="Reminder Off">
              <vs-icon icon="notifications_none" color="primary"></vs-icon>
            </vs-tooltip>
          </div>
        </vs-list-item>
      </vs-alert>
    </vs-list>
  </div>
</template>


<script>
export default {
  name: "Task",
  props: {
    text: String,
    day: String,
    reminder: Boolean,
    id: Number,
  },
  methods: {
    deleteTask(id) {
      this.$emit("delete-task", id);
    },
  },
  emits: ["delete-task"],
};
</script>

<style scoped>
.task {
  margin: 6px 0;
}
</style>
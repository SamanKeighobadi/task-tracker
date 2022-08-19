<template>
  <form @submit="onSubmit">
    <div class="center content-inputs">
      <vs-input
        label="Text"
        type="text"
        name="text"
        v-model="text"
        placeholder="add new task"
      />
    </div>
    <div>
      <vs-input
        label="Day & Time"
        type="text"
        name="day"
        v-model="day"
        placeholder="add day and time"
      />
    </div>
    <div>
      <vs-checkbox v-model="reminder"> Reminder </vs-checkbox>
    </div>

    <vs-input type="submit" value="Save Task" />
    <!-- <vs-button >
        Save Task
    </vs-button> -->
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if (!this.text) {
        alert("Please add a text ");
        return;
      }

      const newTask = {
        id: Math.floor(Math.random() * 1000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this.$emit("add-task", newTask);
      this.$vs.notification({
        title:"Task created"
      })

      this.text = " ";
      this.day = " ";
      this.reminder = false;
    },
  },
};
</script>
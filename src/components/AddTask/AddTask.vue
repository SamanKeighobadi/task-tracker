<template>
  <form @submit="onSubmit">
    <div>
      <label for="text">Text</label>
      <input
        type="text"
        name="text"
        v-model="text"
        placeholder="add new task"
      />
    </div>
    <div>
      <label for="day">Day & Time</label>
      <input
        type="text"
        name="day"
        v-model="day"
        placeholder="add day and time"
      />
    </div>
    <div>
      <label for="Text">reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
    </div>

    <input type="submit" value="Save Task" />
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

      this.$emit("add-task",newTask)

      this.text = " ";
      this.day = " ";
      this.reminder = false;
    },
  },
};
</script>
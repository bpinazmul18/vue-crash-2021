<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label for="text">Task</label>
      <input
        type="text"
        id="text"
        v-model="text"
        name="text"
        placeholder="Add Task"
      />
    </div>
    <span class="error">{{ error ? "Do not empty!" : " " }}</span>
    <div class="form-control">
      <label for="time">Day & Time</label>
      <input
        type="text"
        id="time"
        v-model="day"
        name="day"
        placeholder="Add Day & Time"
      />
    </div>
    <div class="form-control form-control-check">
      <label for="reminder">Set Reminder</label>
      <input type="checkbox" id="reminder" v-model="reminder" name="reminder" />
    </div>

    <input type="submit" value="Save Task" class="btn btn-block" />
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
      error: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if (!this.text) {
        this.error = true;
        return;
      }

      const newTask = {
        // id: Math.floor(Math.random() * 1000000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this.$emit("add-task", newTask);

      this.text = "";
      this.day = "";
      this.reminder = false;
      this.error = false;
    },
  },
};
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.error {
  color: red;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>

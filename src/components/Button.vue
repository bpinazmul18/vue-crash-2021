<template>
  <button @click="addTaskHandler()" :style="{ background: color }" class="btn">
    Add Task
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    Button: {
      text: String,
    },
    color: String,
  },
  methods: {
    addTaskHandler() {
      console.log("you click me!");
    },
  },
};
</script>

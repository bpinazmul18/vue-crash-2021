<template>
  <button
    v-on:click="addTaskHandler"
    :style="{ background: color }"
    class="btn"
  >
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
    addTaskHandler(e) {
      console.log("you click me!", e);
    },
  },
};
</script>

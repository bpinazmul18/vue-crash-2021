<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>
      {{ task.text }}
      <i v-on:click="handleDelete(task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods: {
    handleDelete(id) {
      console.log(id);
    },
  },
};
</script>

<style scoped>
.fas {
  color: red;
}

.fas:hover {
  cursor: pointer;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  /*cursor: pointer;*/
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>

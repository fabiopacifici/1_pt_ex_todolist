<script>
export default {
  name: 'App',
  data() {
    return {
      tasks: [
        {
          text: 'Learn HTML',
          done: true
        },
        {
          text: 'Learn CSS',
          done: true
        },
        {
          text: 'Learn Vue',
          done: false
        }
      ]
      /* tasks: ['task 1', 'task 2'] */
    }
  },
  methods: {
    removeTask(index){
      console.log('rimuovi questa task!!!', index);
      this.tasks.splice(index, 1);
    }
  }
}
</script>

<template>
  <h1>Todo List</h1>
  
  <ul v-if="tasks.length > 0">
    <li v-for="(task, index) in tasks">
      <!-- Option 1 con style binding -->
      <span :style="{ textDecoration: task.done ? 'line-through' : '' }">
        {{ task.text }}


       
        <span v-on:click="removeTask(index)">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-x-circle"
            viewBox="0 0 16 16">
            <path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14m0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16" />
            <path
              d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708" />
          </svg>
        </span>

      </span>

      <!-- Option 1 con class binding 
      <span v-bind:class="{ 'text-decoration-line-through': task.done }">
        {{ task.text }}
      </span>-->

    </li>
  </ul>
  <p v-else>
    😎 Nothing left to do! Enjoy your day 🌞
  </p>


</template>

<style></style>

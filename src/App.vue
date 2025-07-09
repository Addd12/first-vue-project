<script>
export default {
  data(){
    return {
      name: 'John Doe',
      status: 'active',
      tasks: ['Task 1', 'Task 2', 'Task 3'],
      link: 'https://google.com'
    };
  },
  methods: {
    toggleStatus(){
      if(this.status === 'active'){
        this.status = 'pending';
      } else if (this.status === 'pending') {
        this.status = 'inactive';
      } else {
        this.status = 'inactive';
      }
    }
  },
};
</script>
<template>
  <h1 >{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks list</h3>
  <p v-for="task in tasks" :key="task">{{ task }}</p>
  <!-- <a v-bind:href="link">Click for google</a> -->
  <a :href="link">Click for google</a>
  <br />
  <!-- <button v-on:click="toggleStatus">Change status</button> -->
  <button @click="toggleStatus">Change status</button>
</template>

<script>
  export default {
    data(){
      return {
        name: 'norvin',
        message: 'hello',
        status: 'pending',
        tasks: ['Task One', 'Task Two', 'Task Three'],
        link: 'https://github.com/PleaseHelpNorvin'
      };
    },
    
    methods: {
      clickMe() {
        console.log('button clicked');
        this.status = !this.status;
      },
      toggleStatus() {
        if(this.status ==='active'){
          this.status = 'pending';
        }else if (this.status === 'pending'){
          this.status = 'active';
        }else {
          this.status = 'active';
        }
      }
    },
  };
</script>

<template>
   <h1>{{ message }}, {{ name }}</h1>
   <p v-if="status === 'active'">User is active</p>
   <p v-else-if="status === 'pending' ">User is pending</p>
   <p v-else>User is inactive</p>

   <h3>Tasks:</h3>
   <ul>
      <li v-for="task in tasks" :key="task">{{ task }}</li>
   </ul>
   <button @click="clickMe">click me</button>
   <a :href="link">Click for link</a>
   <button v-on:click="toggleStatus">toggle status</button>
   <button @click="toggleStatus">change status</button>
</template>

<style scoped>
  h1{
    background-color: rgb(177, 143, 143);
  }
</style>
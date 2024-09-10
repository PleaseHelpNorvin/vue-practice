<script>
  import {ref} from 'vue';

  export default {
    setup(){
      const name = ref('John Doe');
      const status = ref('active');
      const tasks = ref(['task 1','task 2','task 3']);
      const link = ref('https://github.com/PleaseHelpNorvin');

      const toggleStatus = () => {
        if (status.value === 'active'){
          status.value = 'pending';
        }else if(status.value === 'pending'){
          status.value = 'inactive';
        }else {
          status = 'active';
        }
      }

      return{
        name,
        status,
        tasks,
        toggleStatus,
        link,
      };
    },
  }
</script>

<template>
   <h1> {{ name }}</h1>
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
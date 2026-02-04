<template>
    <div>
      <h2 class="title">Student List</h2>
  
      <p v-if="loading" class="status">Loading students...</p>
      <p v-if="error" class="error">{{ error }}</p>
  
      <StudentComponent
        v-for="student in students"
        :key="student.id"
        :name="student.name"
        course="Computer Science"
        :year="3"
      />
    </div>
  </template>
  
  <script>
  import StudentComponent from '../components/StudentComponent.vue'
  
  export default {
    components: {
      StudentComponent
    },
    data() {
      return {
        students: [],
        loading: true,
        error: null
      }
    },
    async mounted() {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/users')
        if (!response.ok) {
          throw new Error('Failed to load student data')
        }
        this.students = await response.json()
      } catch (err) {
        this.error = err.message
      } finally {
        this.loading = false
      }
    }
  }
  </script>
  
  <style scoped>
  .title {
    color: #4a90e2;
    margin-bottom: 20px;
  }
  
  .status {
    color: #555;
  }
  
  .error {
    color: red;
    font-weight: bold;
  }
  </style>
  
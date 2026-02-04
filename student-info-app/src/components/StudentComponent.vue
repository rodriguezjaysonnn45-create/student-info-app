<template>
    <div class="student-card">
      <h3>{{ name }}</h3>
      <p><strong>Course:</strong> {{ course }}</p>
      <p><strong>Year:</strong> {{ year }}</p>
  
      <button @click="toggleDetails">
        {{ showDetails ? 'Hide' : 'Show' }} Details
      </button>
  
      <p v-if="showDetails" class="details">
        ✔ Student is currently enrolled and active.
      </p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      name: String,
      course: String,
      year: Number
    },
    data() {
      return {
        showDetails: false
      }
    },
    methods: {
      toggleDetails() {
        this.showDetails = !this.showDetails
      }
    }
  }
  </script>
  
  <style scoped>
  .student-card {
    background: white;
    border-radius: 12px;
    padding: 20px;
    margin-bottom: 20px;
    box-shadow: 0 6px 16px rgba(0, 0, 0, 0.08);
  }
  
  h3 {
    color: #4a90e2;
    margin-bottom: 8px;
  }
  
  button {
    margin-top: 10px;
    background: #4a90e2;
    color: white;
    border: none;
    padding: 8px 14px;
    border-radius: 6px;
    cursor: pointer;
  }
  
  button:hover {
    background: #357abd;
  }
  
  .details {
    margin-top: 10px;
    color: #2c7be5;
  }
  </style>
  
<template>
    <header class="header">
      <h1>🎓 Student Info App</h1>
      <nav>
        <router-link to="/" active-class="active">Home</router-link>
        <router-link to="/students" active-class="active">Students</router-link>
      </nav>
    </header>
  </template>
  
  <style scoped>
  .header {
    background: linear-gradient(135deg, #6fb1fc, #a1d8ff);
    padding: 20px;
    color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  nav a {
    margin-left: 15px;
    color: white;
    font-weight: 500;
  }
  
  .active {
    border-bottom: 2px solid white;
  }
  </style>
  
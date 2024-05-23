<template>
    <nav class="navbar">
      <div class="logo">ADLV</div>
      <ul class="nav-links">
        <li><a href="#home"><i class="fas fa-home"></i> Home</a></li>
        <li><a href="#products"><i class="fas fa-tshirt"></i> Clothing</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'Navbar'
  }
  </script>
  
  <style>
  .navbar {
    display: flex;
    align-items: center; /* Center items vertically */
    justify-content: space-between;
    background-color: #794e48;
    padding: 10px;
  }
  
  .logo {
    color: #fff;
    font-size: 50px;
    font-weight: bold;
    text-align: center;
  }
  
  .nav-links {
    list-style: none;
    display: flex;
  }
  
  .nav-links li {
    margin: 0 10px;
  }
  
  .nav-links a {
    color: #fff;
    text-decoration: none;
  }
  
  /* Adjust icon size */
  .nav-links a i {
    margin-right: 5px; /* Add some space between the icon and text */
    font-size: 18px; /* Adjust the icon size */
  }
  </style>
<template>
  <nav class="navbar">
    <div class="logo">Naufal Sport</div>
    <ul class="nav-links">
      <li><a href="#home">Home</a></li>
      <li><a href="#products">Products</a></li>
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
  justify-content: space-between;
  align-items: center; /* Rata tengah secara vertikal */
  background-color: #1dc7e1;
  padding: 10px;
}

.logo {
  color: #0b0b0b;
  font-size: 24px;
  font-family: 'Broadway'
  
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


</style>

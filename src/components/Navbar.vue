<template>
  <nav class="navbar">
    <div class="container">
      <div class="navbar-brand">
        <a href="#home">MyPortfolio</a>
      </div>
      <ul class="navbar-menu">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <button class="navbar-toggle" @click="toggleMenu">
        <i class="fas fa-bars"></i>
      </button>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  methods: {
    toggleMenu() {
      const menu = document.querySelector(".navbar-menu");
      menu.classList.toggle("active");
    },
  },
};
</script>

<style scoped>
.navbar {
  background-color: white;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  animation: slideDown 0.5s ease-out forwards;
}

.navbar .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 20px;
}

.navbar-brand a {
  font-size: 1.5rem;
  font-weight: bold;
  color: #17bedb;
  text-decoration: none;
}

.navbar-menu {
  display: flex;
  list-style: none;
}

.navbar-menu li {
  margin-left: 30px;
}

.navbar-menu a {
  text-decoration: none;
  color: #333;
  transition: color 0.3s ease;
  font-weight: 500;
}

.navbar-menu a:hover {
  color: #42b983;
}

.navbar-toggle {
  display: none;
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  color: #42b983;
}

@keyframes slideDown {
  from {
    transform: translateY(-100%);
  }
  to {
    transform: translateY(0);
  }
}

@media (max-width: 768px) {
  .navbar-menu {
    position: fixed;
    top: 70px;
    left: 0;
    width: 100%;
    background: white;
    flex-direction: column;
    align-items: center;
    padding: 20px 0;
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
    transform: translateY(-150%);
    transition: transform 0.3s ease;
  }

  .navbar-menu.active {
    transform: translateY(0);
  }

  .navbar-menu li {
    margin: 10px 0;
  }

  .navbar-toggle {
    display: block;
  }
}
</style>

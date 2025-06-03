<template>
  <section id="home" class="section hero">
    <div class="container">
      <h1 class="fade-in">
        Hello Guys, I'm <span class="highlight">ALIF BASMAN MAKARIM</span>
      </h1>
    </div>
  </section>
</template>

<script>
export default {
  name: "HomeSection",
};
</script>

<style scoped>
.hero {
  background: linear-gradient(135deg, #ADD8E6 0%, #35495e 100%);
  color: white;
  text-align: center;
}

.hero h1 {
  font-size: 3rem;
  margin-bottom: 20px;
}

.hero .highlight {
  color: #1ccacd;
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2rem;
  }
}
</style>

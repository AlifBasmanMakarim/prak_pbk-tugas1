<template>
  <section id="about" class="section">
    <div class="container">
      <h2 class="section-title">About Me</h2>
      <div class="about-content">
        <div class="about-text">
          <div class="profile">
            <img
              src="/src/assets/Profil.jpg"
              alt="Profile"
              class="profile-image"
            />
            <div class="profile-info">
              <h3>ALIF BASMAN MAKARIM</h3>
              <p>Web Developer</p>
            </div>
          </div>

          <p class="bio">
            Halo, saya Alif Basman Makarim, seorang Web Developer yang 
            berfokus pada pengembangan antarmuka web yang modern dan responsif. 
            Saya memiliki keahlian utama di Vue.js, framework JavaScript yang saya gunakan untuk membangun 
            aplikasi front-end yang cepat dan efisien. Selain itu, saya juga terbiasa bekerja dengan 
            JavaScript, HTML, dan CSS untuk menciptakan tampilan yang menarik dan fungsional. Dengan kombinasi teknologi ini, 
            saya berkomitmen untuk menghadirkan solusi web yang tidak hanya powerful, tetapi juga memiliki pengalaman pengguna yang optimal.
          </p>

          <div class="social-media">
            <div class="social-links">
              <a
                v-for="social in socialMedia"
                :key="social.name"
                :href="social.url"
                target="_blank"
                :title="social.name"
                class="social-link"
                :style="{ backgroundColor: social.color }"
              >
                <i :class="social.icon"></i>
              </a>
            </div>
          </div>
        </div>

        <div class="skills">
          <h3>My Skills</h3>
          <ul>
            <li
              v-for="(skill, index) in skills"
              :key="index"
              class="skill-item"
            >
              {{ skill }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AboutSection",
  data() {
    return {
      skills: ["Vue.js", "JavaScript", "HTML", "CSS"],
      socialMedia: [
        // {
        //   name: "LinkedIn",
        //   url: "https://linkedin.com",
        //   icon: "fab fa-linkedin-in",
        //   color: "#0077b5"
        // }
      ],
    };
  },
};
</script>

<style scoped>
.section-title {
  margin-bottom: 40px;
  font-size: 2rem;
  color: #87cefa;
  text-align: center;
}

.about-content {
  display: flex;
  gap: 50px;
  flex-direction: row-reverse; /* Pindahkan About ke kanan */
}

.about-text {
  flex: 1;
}

.profile {
  display: flex;
  align-items: center;
  margin-bottom: 30px;
  animation: fadeIn 1s ease-in forwards;
}

.profile-image {
  width: 100px;
  height: 100px;
  border-radius: 0; /* Persegi */
  object-fit: cover;
  margin-right: 20px;
  border: 3px solid #87cefa;
}

.profile-info h3 {
  font-size: 1.5rem;
  margin-bottom: 5px;
  color: #4682b4;
}

.profile-info p {
  color: #666;
}

.bio {
  margin-bottom: 30px;
  line-height: 1.8;
  color: #555;
}

.skills {
  flex: 1;
}

.skills h3 {
  margin-bottom: 20px;
  font-size: 1.5rem;
  color: #4682b4;
}

.skills ul {
  list-style: none;
}

.skill-item {
  background: #e0f7ff;
  margin-bottom: 10px;
  padding: 12px 15px;
  border-radius: 5px;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.skill-item:hover {
  background: #87cefa;
  color: white;
  transform: translateX(10px);
}

.skill-item::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 5px;
  height: 100%;
  background: #4682b4;
  transition: all 0.3s ease;
}

.skill-item:hover::before {
  background: white;
}

.social-media {
  margin-top: 30px;
}

.social-media h3 {
  margin-bottom: 15px;
  font-size: 1.2rem;
  color: #4682b4;
}

.social-links {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 45px;
  height: 45px;
  color: white;
  border-radius: 50%;
  font-size: 1.2rem;
  transition: all 0.3s ease;
  text-decoration: none;
  position: relative;
  overflow: hidden;
}

.social-link:hover {
  transform: translateY(-5px) scale(1.1);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

.social-link::after {
  content: "";
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(255, 255, 255, 0.2),
    transparent
  );
  transition: 0.5s;
}

.social-link:hover::after {
  left: 100%;
}

@media (max-width: 768px) {
  .about-content {
    flex-direction: column; /* Tetap vertical di mobile */
  }

  .profile {
    flex-direction: column;
    text-align: center;
  }

  .profile-image {
    margin-right: 0;
    margin-bottom: 15px;
    width: 150px;
    height: 150px;
  }

  .social-links {
    justify-content: center;
  }
}
</style>

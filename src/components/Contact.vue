<template>
  <section id="contact" class="section">
    <div class="container">
      <h2 class="section-title">KONTAK</h2>
      <div class="contact-container">
        <form @submit.prevent="submitForm" class="contact-form">
          <div class="form-group">
            <label for="name">Name</label>
            <input
              type="text"
              id="name"
              v-model="form.name"
              required
              class="form-input"
              placeholder="Your name"
            />
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input
              type="email"
              id="email"
              v-model="form.email"
              required
              class="form-input"
              placeholder="Your email"
            />
          </div>
          <div class="form-group">
            <label for="subject">Subject</label>
            <input
              type="text"
              id="subject"
              v-model="form.subject"
              required
              class="form-input"
              placeholder="Subject"
            />
          </div>
          <div class="form-group">
            <label for="message">Message</label>
            <textarea
              id="message"
              v-model="form.message"
              required
              class="form-input"
              rows="5"
              placeholder="Your message"
            ></textarea>
          </div>
          <button type="submit" class="btn">Send Message</button>
        </form>

        <div class="contact-info">
          <h3>KONTAK INFOMASI</h3>
          <div class="info-item">
            <i class="fas fa-envelope"></i>
            <span>alifbasman@gmail.com</span>
          </div>
          <div class="info-item">
            <i class="fas fa-phone"></i>
            <span>+628 6677 3231 90</span>
          </div>
          <div class="info-item">
            <i class="fas fa-map-marker-alt"></i>
            <span>Marpoyan, Pekanbaru, Riau, Indonesia</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "ContactSection",
  data() {
    return {
      form: {
        name: "",
        email: "",
        subject: "",
        message: "",
      },
    };
  },
  methods: {
    submitForm() {
      alert(`Thank you ${this.form.name}, your message has been sent!`);
      this.form = {
        name: "",
        email: "",
        subject: "",
        message: "",
      };
    },
  },
};
</script>

<style scoped>
.contact-container {
  display: flex;
  gap: 50px;
}

.contact-form {
  flex: 1;
  background: white;
  padding: 30px;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  animation: fadeIn 1s ease-in forwards;
}

.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  margin-bottom: 8px;
  font-weight: bold;
  color: #35495e;
}

.form-input {
  width: 100%;
  padding: 12px;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.form-input:focus {
  border-color: #42b983;
  outline: none;
  box-shadow: 0 0 0 3px rgba(66, 185, 131, 0.2);
}

textarea.form-input {
  resize: vertical;
  min-height: 120px;
}

.contact-info {
  flex: 1;
  background: #35495e;
  padding: 30px;
  border-radius: 10px;
  color: white;
}

.contact-info h3 {
  margin-bottom: 20px;
  font-size: 1.5rem;
  position: relative;
  padding-bottom: 10px;
}

.contact-info h3::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 50px;
  height: 3px;
  background: #42b983;
}

.info-item {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.info-item i {
  font-size: 1.2rem;
  margin-right: 15px;
  color: #42b983;
}

.info-item span {
  font-size: 1rem;
}

@media (max-width: 768px) {
  .contact-container {
    flex-direction: column;
  }

  .contact-info {
    order: -1;
    margin-bottom: 30px;
  }
}
</style>

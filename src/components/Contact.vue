<template>
  <div class="contact-container">
    <div class="contact-card" id="contact-card">
      <div class="contact-item">
        <img :src="whatsappLogo" alt="WhatsApp Logo" class="contact-logo">
        <p class="contact-text">(52) 55 63 16 81 83</p>
      </div>
      <div class="contact-item">
        <img :src="phoneLogo" alt="Teléfono Logo" class="contact-logo">
        <p class="contact-text">55 92 35 33 99</p>
      </div>
      <div class="contact-item">
        <img :src="emailLogo" alt="Correo Logo" class="contact-logo">
        <p class="contact-text">info@ketza.org</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import whatsappLogo from '../assets/whatsapp.png';
import phoneLogo from '../assets/telefono.png';
import emailLogo from '../assets/correo.png';
</script>

<style scoped>
.contact-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 20px;
  height: 50vh;
  box-sizing: border-box;
}

.contact-card {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap; /* Allow items to wrap if necessary */
  padding: 5vh 20px;
  background: #D4D4D4;
  border: 2px solid #253743;
  border-radius: 10px;
  max-width: 90%;
  width: 100%;
  box-sizing: border-box;
}

/* Contact Item Styles */
.contact-item {
  display: flex;
  align-items: center;
  margin-bottom: 2vh;
  word-wrap: break-word; /* Allow long words to break and wrap */
}

/* Image Styles */
.contact-logo {
  width: 2.5em; /* Use relative units */
  height: 2.5em;
  margin-right: 0.625em;
}

/* Text Styles */
.contact-text {
  font-size: 1rem;
  font-weight: 400;
  color: #202020;
  margin: 0;
  word-break: break-all; /* Prevent long text from overflowing */
}

/* Desktop Styles */
@media (min-width: 769px) {
  .contact-card {
    flex-direction: row;
    justify-content: space-around;
    max-width: 80%;
    padding: 5vh 40px;
  }

  .contact-item {
    margin-bottom: 0;
    max-width: 30%; /* Ensure items don't exceed available space */
  }

  .contact-logo {
    width: 2.5em;
    height: 2.5em;
    margin-right: 0.9375em;
  }

  .contact-text {
    font-size: .9rem;
  }
}

/* Mobile Styles */
@media (max-width: 768px) {
  .contact-card {
    flex-direction: column;
    max-width: 100%;
    padding: 5vh 20px;
  }

  .contact-item {
    width: 100%; /* Ensure items take full width */
    margin-bottom: 2vh;
  }

  .contact-logo {
    width: 2em; /* Slightly smaller icons for better fit */
    height: 2em;
    margin-right: 0.5em;
  }

  .contact-text {
    font-size: 1rem;
  }
}
</style>
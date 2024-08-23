<template>
  <div class="contact-container">
    <router-link to="/" class="back-button">
      <i class="fa fa-arrow-left icon"></i>
    </router-link>
    <div class="contact-content">
      <div class="contact-form">
        <h2>Chat to our team</h2>
        <p class="subtitle">
          Need help with something? Want a demo? Get in touch with our friendly team, and we'll get
          back to you within 2 hours.
        </p>
        <form>
          <div class="input-group">
            <div class="input-container">
              <i class="fa fa-user input-icon"></i>
              <input type="text" placeholder="First name" />
            </div>
            <div class="input-container">
              <i class="fa fa-user input-icon"></i>
              <input type="text" placeholder="Last name" />
            </div>
          </div>
          <div class="input-group">
            <div class="input-container">
              <i class="fa fa-briefcase input-icon"></i>
              <input type="text" placeholder="Job title" />
            </div>
            <div class="input-container">
              <i class="fa fa-envelope input-icon"></i>
              <input type="email" placeholder="Work email" />
            </div>
          </div>
          <div class="input-group">
            <div class="input-container">
              <i class="fa fa-phone input-icon"></i>
              <input type="tel" placeholder="+1 (555) 000-0000" />
            </div>
          </div>
          <!-- New Message Input -->
          <div class="input-group full-width">
            <div class="input-container message-container">
              <i class="fa fa-comment input-icon message-icon"></i>
              <textarea placeholder="Your message" rows="4"></textarea>
            </div>
          </div>
          <button type="submit" class="submit-button">Get in touch</button>
        </form>
      </div>
      <div class="contact-image">
        <img src="../assets/contactimg.png" alt="Contact Image" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactPage'
}
</script>

<style scoped>
.contact-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  font-family: 'Poppins', sans-serif;
  background-color: #f0f4f8;
  padding: 20px;
}

.contact-content {
  display: flex;
  max-width: 1000px;
  width: 100%;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  background-color: #fff;
  height: 85vh;
  flex-direction: row;
}

.contact-form {
  flex: 1;
  padding: 30px;
}

.contact-form h2 {
  font-size: 24px;
  margin-bottom: 15px;
  font-family: 'Orbitron', sans-serif;
  color: #319cb7;
}

.subtitle {
  color: #000056;
  margin-bottom: 25px;
  font-size: 14px;
}

.input-group {
  margin-bottom: 20px;
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}

.input-group.full-width {
  flex-direction: column;
}

.input-container {
  position: relative;
  flex: 1;
}

.input-container.message-container {
  width: 100%;
}

.input-icon {
  position: absolute;
  left: 12px;
  top: 50%;
  transform: translateY(-50%);
  color: #319cb7;
  font-size: 16px;
}

.message-icon {
  top: 18px;
}

input,
textarea {
  width: 100%;
  padding: 10px 12px 10px 40px;
  border: 1px solid #ccc;
  font-size: 14px;
  border-radius: 25px;
  box-sizing: border-box;
  transition: border-color 0.3s;
}

textarea {
  resize: vertical; /* Allows the textarea to be resized */
  border-radius: 25px;
  padding: 12px 40px; /* Matches the input padding */
  min-height: 120px; /* Sets a default height for the textarea */
}

input:focus,
textarea:focus {
  border-color: #319cb7;
  outline: none;
  box-shadow: 0 0 0 2px rgba(59, 130, 246, 0.2);
}

.submit-button {
  width: 100%;
  padding: 12px;
  background-color: #319cb7;
  color: white;
  font-size: 16px;
  cursor: pointer;
  border: none;
  border-radius: 25px;
  height: 45px;
  margin-top: 4px;
  transition: background-color 0.3s;
}

.submit-button:hover {
  background-color: #d2fbff;
  color: #000056;
}

.contact-image {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

.contact-image img {
  width: 100%;
  height: auto;
  border-radius: 0 20px 20px 0;
}

.back-button {
  position: absolute;
  top: 15px;
  left: 15px;
  background-color: #319cb7;
  color: white;
  border: none;
  border-radius: 50%;
  padding: 10px 13px;
  font-size: 18px;
  cursor: pointer;
  transition: background-color 0.3s;
  text-decoration: none;
}

.back-button .icon {
  margin: 0;
}

.back-button:hover {
  background-color: #abdee4;
}

/* Responsive Styles */
@media screen and (max-width: 768px) {
  .contact-content {
    flex-direction: column;
    height: auto;
  }

  .contact-image {
    display: none;
  }

  .contact-form {
    padding: 20px;
    height: auto;
  }

  .input-group {
    flex-direction: column;
  }
}

@media screen and (max-width: 480px) {
  .contact-form h2 {
    font-size: 20px;
  }

  .subtitle {
    font-size: 13px;
  }

  .input-group {
    gap: 2px;
  }

  .submit-button {
    height: 40px;
    font-size: 14px;
  }
}
</style>

<template>
  <div class="features-section">
    <div class="features-header">
      <button class="feature-tag">About Us</button>
      <h2 class="animated-text">
        AI-Powered<span class="highlight"> Face & Emotion</span> Detection Web App
      </h2>
      <p class="animated-text">
        Experience the future of AI technology with our cutting-edge web app.
      </p>
    </div>
    <div class="features-content">
      <div class="features-video">
        <video autoplay loop class="animated-video video-1" controls>
          <source src="../assets/about-video-new.mp4" type="video/mp4" />
          Your browser does not support the video tag.
        </video>
      </div>
      <div class="features-text">
        <h2 class="animated-text title">About the project</h2>
        <p class="animated-text paragraph">
          The goal of the project was to develop an advanced face and emotion detection web
          application. Utilizing the latest AI technologies, our app offers real-time analytics and
          insights into user emotions and identities.
        </p>
        <p class="animated-text paragraph">
          By leveraging sophisticated algorithms, our solution provides accurate and efficient
          emotion detection, helping businesses understand user behavior and enhance customer
          experiences. The AI-powered system ensures privacy and security, adhering to the highest
          standards.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FeaturesSection',
  mounted() {
    const options = {
      root: null,
      rootMargin: '0px',
      threshold: 0.1
    }

    const callback = (entries, observer) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('in-view')
          observer.unobserve(entry.target)
        }
      })
    }

    const observer = new IntersectionObserver(callback, options)

    document.querySelectorAll('.animated-text, .animated-video').forEach((el) => {
      observer.observe(el)
    })
  }
}
</script>

<style scoped>
features-section {
  background-color: white;
  padding: 60px 20px;
  border-radius: 10px;
  margin: 10px;
  display: flex;
  flex-direction: row;
}

.features-header {
  text-align: center;
  margin-bottom: 40px;
}

.feature-tag {
  border: none;
  cursor: default;
  background-color: #abdee4;
  color: #00175a;
  padding: 7px 10px;
  border-radius: 20px;
  font-weight: 600;
}

.features-header h2 {
  font-size: 36px;
  color: #00175a;
  margin-top: 10px;
  margin-bottom: 10px;
  font-family: 'orbitron', sans-serif;
  font-optical-sizing: auto;
  font-style: normal;
}

.features-header h2 .highlight {
  color: #1992a8;
}

.features-header p {
  font-size: 16px;
  margin-bottom: 20px;
}

/* Animation for the video */
.animated-video {
  width: 70%;
  height: auto;
  opacity: 0;
  transform: translateY(20px);
  transition:
    opacity 2s ease-out,
    transform 2s ease-out;
  margin-top: 120px;
  margin-bottom: 50px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  margin-left: 50px;
}

.animated-video.in-view {
  opacity: 1;
  transform: translateY(0);
}

.animated-video.video-1 {
  animation: floatAnimation 4s ease-in-out infinite;
}

/* Animation for the text */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animated-text {
  opacity: 0;
  color: #00175a;
  transform: translateY(20px);
  transition:
    opacity 2s ease-out,
    transform 2s ease-out;
}

.animated-text.in-view {
  opacity: 1;
  transform: translateY(0);
}

.features-content {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
}

.features-video {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 40px;
}

.features-text {
  flex: 1;
  color: #00175a;
  background-color: aliceblue;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transform: translateY(30px);
  margin-right: 40px;
}

.features-text h2 {
  font-size: 36px;
  color: #289bb6;
  font-family: 'orbitron', sans-serif;
  margin-bottom: 20px;
}

.features-text p {
  font-size: 16px;
  color: #00175a;
  line-height: 1.6;
  margin-bottom: 20px;
}

/* Media Queries for Responsiveness */

@media (max-width: 768px) {
  .features-content {
    flex-direction: column; /* Stack items vertically on smaller screens */
  }

  .features-video {
    margin-right: 0; /* Remove margin for stacked layout */
    margin-bottom: 20px; /* Add space between video and text */
  }

  .features-text {
    padding: 15px; /* Adjust padding */
  }
}

@media (max-width: 480px) {
  .features-section {
    padding: 20px; /* Reduce padding for very small screens */
  }

  .features-video {
    margin-bottom: 20px; /* Ensure spacing is consistent */
  }

  .features-text {
    padding: 15px;
  }

  .features-header h2 {
    font-size: 24px; /* Further decrease font size for very small screens */
  }

  .features-header p {
    font-size: 13px;
  }

  .features-text h2 {
    font-size: 24px; /* Further decrease title size for very small screens */
  }

  .features-text p {
    font-size: 13px; /* Further decrease paragraph size for very small screens */
  }
}

/* Animation for the video */
.animated-video {
  width: 100%;
  height: auto;
  opacity: 0;
  transform: translateY(20px);
  transition:
    opacity 2s ease-out,
    transform 2s ease-out;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.animated-video.in-view {
  opacity: 1;
  transform: translateY(0);
}

.animated-video.video-1 {
  animation: floatAnimation 4s ease-in-out infinite;
}
.features-section {
  background-color: white;
  padding: 60px 20px;
  border-radius: 10px;
  margin: 0 auto; /* Center the section */
}

.features-header {
  text-align: center;
}

.feature-tag {
  border: none;
  cursor: default;
  background-color: #abdee4;
  color: #00175a;
  padding: 7px 10px;
  border-radius: 20px;
  font-weight: 600;
}

.features-header h2 {
  font-size: 36px;
  color: #00175a;
  margin-top: 10px;
  margin-bottom: 10px;
  font-family: 'orbitron', sans-serif;
}

.features-header h2 .highlight {
  color: #1992a8;
}

.features-header p {
  font-size: 16px;
  margin-bottom: 20px;
}

/* Animation for the video */
.animated-video {
  width: 100%;
  height: auto;
  opacity: 0;
  transform: translateY(20px);
  transition:
    opacity 2s ease-out,
    transform 2s ease-out;
  margin-top: 120px;
  margin-bottom: 50px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.animated-video.in-view {
  opacity: 1;
  transform: translateY(0);
}

.animated-video.video-1 {
  animation: floatAnimation 4s ease-in-out infinite;
}

/* Animation for the text */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animated-text {
  opacity: 0;
  color: #00175a;
  transform: translateY(20px);
  transition:
    opacity 2s ease-out,
    transform 2s ease-out;
}

.animated-text.in-view {
  opacity: 1;
  transform: translateY(0);
}

.features-video {
  width: 100%;
  max-width: 600px; /* Limit the width of the video */
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 90px;
}

.features-text {
  width: 100%;
  max-width: 600px; /* Limit the width of the text box */
  color: #00175a;
  background-color: aliceblue;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transform: translateY(30px);
  margin-bottom: 60px;
}

.features-text h2 {
  font-size: 36px;
  color: #289bb6;
  font-family: 'orbitron', sans-serif;
  margin-bottom: 20px;
}

.features-text p {
  font-size: 16px;
  color: #00175a;
  line-height: 1.6;
  margin-bottom: 20px;
}

/* Media Queries for Responsiveness */

@media (max-width: 1024px) {
  .features-header h2 {
    font-size: 32px; /* Adjust font size for tablets */
  }

  .features-header p {
    font-size: 15px; /* Adjust font size for tablets */
  }

  .features-text h2 {
    font-size: 32px; /* Adjust title size for tablets */
  }

  .features-text p {
    font-size: 15px; /* Adjust paragraph size for tablets */
  }
}

@media (max-width: 768px) {
  .features-header h2 {
    font-size: 28px; /* Further decrease font size for smaller screens */
  }

  .features-header p {
    font-size: 14px;
  }

  .features-text h2 {
    font-size: 28px; /* Further decrease title size for smaller screens */
  }

  .features-text p {
    font-size: 14px; /* Further decrease paragraph size for smaller screens */
  }
}

@media (max-width: 480px) {
  .features-section {
    padding: 20px; /* Reduce padding for very small screens */
  }

  .features-video {
    margin-top: 0;
    margin-bottom: 80px;
  }

  .features-text {
    padding: 15px;
  }

  .features-header h2 {
    font-size: 24px; /* Further decrease font size for very small screens */
  }

  .features-header p {
    font-size: 13px;
  }

  .features-text h2 {
    font-size: 24px; /* Further decrease title size for very small screens */
  }

  .features-text p {
    font-size: 13px; /* Further decrease paragraph size for very small screens */
  }
}
</style>

<script setup>
import { ref } from 'vue'

// Kolom 2: Carousel State
const activeSlide = ref(0)
const slideImages = [
  { src: '/slide1.jpg', alt: 'Yuji Nishida Celebrating' },
  { src: '/slide2.jpg', alt: 'Yuji Nishida Jump Serve' },
  { src: '/slide3.jpg', alt: 'Yuji Nishida Osaka Bluteon' },
  { src: '/slide4.jpg', alt: 'Yuji Nishida Powerful Spike' }
]

const nextSlide = () => {
  activeSlide.value = (activeSlide.value + 1) % slideImages.length
}

const prevSlide = () => {
  activeSlide.value = (activeSlide.value - 1 + slideImages.length) % slideImages.length
}

const goToSlide = (idx) => {
  activeSlide.value = idx
}

// Kolom 4: Mailing List State
const emailInput = ref('')
const isSubscribed = ref(false)

const handleSubscribe = () => {
  if (emailInput.value.trim()) {
    isSubscribed.value = true
    emailInput.value = ''
    setTimeout(() => {
      isSubscribed.value = false
    }, 4000)
  }
}
</script>

<template>
  <section class="hero-wrapper">
    <!-- ==============================================
         KOLOM 1: TRAIN WITH YUJI NISHIDA
         Warna dasar: #8C5858
         Kiri: Teks & button & social media
         Kanan: Foto Nishida dengan tangan di dada
         ============================================== -->
    <div class="hero-col-1">
      <div class="col1-container">
        <!-- Sebelah Kiri: Teks, Deskripsi, Tombol Contact & Social Icons -->
        <div class="col1-content">
          <h1 class="col1-title">TRAIN WITH YUJI NISHIDA</h1>
          
          <p class="col1-description">
            The Mission? To work with aspiring Volleyball & get them more focused, refined, and technically proficient than ever before.
          </p>

          <div class="col1-actions">
            <!-- Social Media Logos di samping kiri Button Contact (W: 140px, H: 24px) -->
            <div class="social-icons-group" aria-label="Social Media Links">
              <!-- Twitter / X -->
              <a href="#" class="social-icon-item" aria-label="Twitter">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
                </svg>
              </a>
              <!-- Facebook -->
              <a href="#" class="social-icon-item" aria-label="Facebook">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                </svg>
              </a>
              <!-- Instagram -->
              <a href="#" class="social-icon-item" aria-label="Instagram">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
                </svg>
              </a>
              <!-- LinkedIn -->
              <a href="#" class="social-icon-item" aria-label="LinkedIn">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                </svg>
              </a>
            </div>

            <!-- Button Contact (W 175px, H 54px) -->
            <a href="#" class="btn-contact-col1">
              CONTACT
            </a>
          </div>
        </div>

        <!-- Sebelah Kanan: Foto Nishida dengan tangan di dada -->
        <div class="col1-image-side">
          <img 
            src="/nishida-chest.jpg" 
            alt="Yuji Nishida hand on chest" 
            class="nishida-chest-photo"
          />
        </div>
      </div>
    </div>

    <!-- ==============================================
         KOLOM 2: WHO IS YUJI NISHIDA?
         Warna dasar: Putih (#ffffff)
         Empat foto Yuji Nishida berbeda yang bisa di-slide
         Teks judul font 32, deskripsi font 20
         ============================================== -->
    <div class="hero-col-2">
      <div class="col2-container">
        <!-- 4 Foto Yuji Nishida Slider -->
        <div class="col2-slider-box">
          <div class="slider-viewport">
            <div 
              class="slider-track" 
              :style="{ transform: `translateX(-${activeSlide * 100}%)` }"
            >
              <div 
                v-for="(img, idx) in slideImages" 
                :key="idx" 
                class="slide-item"
              >
                <img :src="img.src" :alt="img.alt" class="slide-img" />
              </div>
            </div>

            <!-- Slider Arrows -->
            <button class="slider-arrow prev" @click="prevSlide" aria-label="Previous slide">
              &#10094;
            </button>
            <button class="slider-arrow next" @click="nextSlide" aria-label="Next slide">
              &#10095;
            </button>
          </div>

          <!-- Slider Indicators -->
          <div class="slider-dots">
            <span 
              v-for="(_, idx) in slideImages" 
              :key="idx" 
              class="dot" 
              :class="{ 'active': activeSlide === idx }"
              @click="goToSlide(idx)"
            ></span>
          </div>
        </div>

        <!-- Deskripsi Who Is Yuji Nishida -->
        <div class="col2-text-box">
          <h2 class="col2-title">Who Is Yuji Nishida?</h2>
          <p class="col2-paragraph">
            Yuji Nishida is a professional Japanese volleyball player known for his powerful left-handed spikes, explosive jump, 
            and aggressive serving. He plays as an opposite spiker for Osaka Bluteon and represents Japan internationally.
          </p>
        </div>
      </div>
    </div>

    <!-- ==============================================
         KOLOM 3: SMASH IMAGE WITH 4 BUTTONS (2x2)
         Background gambar smash bola Nishida (W: 1512, H: 568)
         Di tengah ada 4 button putih 2x2 font 32:
         1. Curriculum Vitae (Biru)
         2. Online Coaching (Merah)
         3. One to One (Merah)
         4. Elite Programmes (Merah)
         ============================================== -->
    <div class="hero-col-3">
      <div class="col3-banner-container">
        <img 
          src="/nishida-smash.jpg" 
          alt="Yuji Nishida spiking volleyball" 
          class="col3-banner-img"
        />
        <div class="col3-overlay"></div>
        
        <!-- 4 Button Grid (2 x 2) di tengah gambar -->
        <div class="col3-button-grid">
          <button class="col3-btn btn-blue">Curriculum Vitae</button>
          <button class="col3-btn btn-red">Online Coaching</button>
          <button class="col3-btn btn-red">One to One</button>
          <button class="col3-btn btn-red">Elit Programms</button>
        </div>
      </div>
    </div>

    <!-- ==============================================
         KOLOM 4: MAILING LIST (2 BARIS TULISAN & EMAIL INPUT)
         Tulisan 1: "Want to Become a Better Player?" (Font 42, Merah)
         Tulisan 2: "Join The Mailing List For Exclusive Content, Additional Tips & Updates" (Font 18)
         Tempat/kolom pengisian email
         ============================================== -->
    <div class="hero-col-4">
      <div class="col4-container">
        <h3 class="col4-title">Want to Become a Better Player?</h3>
        <p class="col4-subtitle">
          Join The Mailing List For Exclusive Content, Additional Tips & Updates
        </p>

        <form class="col4-form" @submit.prevent="handleSubscribe">
          <div class="email-input-wrapper">
            <input 
              type="email" 
              v-model="emailInput" 
              placeholder="Enter your email address" 
              required 
              class="email-input-field"
            />
            <button type="submit" class="email-submit-btn">
              SUBSCRIBE
            </button>
          </div>
          <p v-if="isSubscribed" class="success-message">
            Thank you for subscribing! Welcome to Team Nishida.
          </p>
        </form>
      </div>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,600;0,700;0,800;0,900;1,800&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');

.hero-wrapper {
  width: 100%;
  display: flex;
  flex-direction: column;
  overflow-x: hidden;
  font-family: 'Plus Jakarta Sans', sans-serif;
}

/* =========================================================
   KOLOM 1 STYLES (#8C5858)
   ========================================================= */
.hero-col-1 {
  width: 100%;
  background-color: #8C5858;
  color: #ffffff;
  padding: 3.5rem 2rem 2.5rem;
  box-sizing: border-box;
}

.col1-container {
  max-width: 1380px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 3rem;
}

.col1-content {
  flex: 1;
  max-width: 780px;
}

.col1-title {
  font-family: 'Montserrat', sans-serif;
  font-size: 64px;
  font-weight: 900;
  line-height: 1.08;
  color: #ffffff;
  margin-bottom: 1.75rem;
  letter-spacing: -0.02em;
}

.col1-description {
  font-size: 26px;
  font-weight: 500;
  line-height: 1.45;
  color: #ffffff;
  margin-bottom: 2.5rem;
}

.col1-actions {
  display: flex;
  align-items: center;
  gap: 2rem;
  flex-wrap: wrap;
}

/* Social media icons W: 140px, H: 24px */
.social-icons-group {
  width: 140px;
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-shrink: 0;
}

.social-icon-item {
  color: #ffffff;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 24px;
  height: 24px;
  transition: transform 0.2s ease, opacity 0.2s ease;
  opacity: 0.95;
}

.social-icon-item:hover {
  transform: translateY(-2px);
  opacity: 1;
}

.social-icon-item svg {
  width: 20px;
  height: 20px;
}

/* Button Contact W: 175px, H: 54px */
.btn-contact-col1 {
  width: 175px;
  height: 54px;
  box-sizing: border-box;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background-color: #e60012;
  color: #ffffff;
  font-family: 'Montserrat', sans-serif;
  font-size: 0.95rem;
  font-weight: 800;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  text-decoration: none;
  border-radius: 4px;
  border: 1px solid #e60012;
  box-shadow: 0 4px 15px rgba(230, 0, 18, 0.35);
  transition: all 0.25s ease;
  cursor: pointer;
  flex-shrink: 0;
}

.btn-contact-col1:hover {
  background-color: #c4000f;
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(230, 0, 18, 0.45);
}

.col1-image-side {
  flex-shrink: 0;
  display: flex;
  justify-content: center;
}

.nishida-chest-photo {
  max-width: 440px;
  width: 100%;
  height: auto;
  max-height: 560px;
  object-fit: cover;
  border-radius: 12px;
  box-shadow: 0 16px 36px rgba(0, 0, 0, 0.25);
}

/* =========================================================
   KOLOM 2 STYLES (Warna dasar: Putih, Slider 4 foto)
   ========================================================= */
.hero-col-2 {
  width: 100%;
  background-color: #ffffff;
  padding: 4.5rem 2rem;
  box-sizing: border-box;
}

.col2-container {
  max-width: 1280px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  gap: 3.5rem;
}

.col2-slider-box {
  flex: 1;
  max-width: 580px;
}

.slider-viewport {
  position: relative;
  width: 100%;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  aspect-ratio: 4 / 3;
}

.slider-track {
  display: flex;
  width: 100%;
  height: 100%;
  transition: transform 0.45s cubic-bezier(0.4, 0, 0.2, 1);
}

.slide-item {
  min-width: 100%;
  height: 100%;
}

.slide-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.slider-arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.5);
  color: #ffffff;
  border: none;
  font-size: 1.25rem;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.2s ease;
  z-index: 5;
}

.slider-arrow:hover {
  background: #e60012;
}

.slider-arrow.prev {
  left: 14px;
}

.slider-arrow.next {
  right: 14px;
}

.slider-dots {
  display: flex;
  justify-content: center;
  gap: 8px;
  margin-top: 1rem;
}

.slider-dots .dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: #cbd5e1;
  cursor: pointer;
  transition: all 0.25s ease;
}

.slider-dots .dot.active {
  background: #e60012;
  width: 24px;
  border-radius: 999px;
}

.col2-text-box {
  flex: 1;
}

.col2-title {
  font-family: 'Montserrat', sans-serif;
  font-size: 32px;
  font-weight: 800;
  color: #111111;
  margin-bottom: 1.25rem;
  line-height: 1.25;
}

.col2-paragraph {
  font-size: 20px;
  font-weight: 400;
  line-height: 1.6;
  color: #4b5563;
}

/* =========================================================
   KOLOM 3 STYLES (Smash W: 1512, H: 568 + 4 Button 2x2)
   ========================================================= */
.hero-col-3 {
  width: 100%;
  background-color: #111111;
  display: flex;
  justify-content: center;
  overflow: hidden;
}

.col3-banner-container {
  position: relative;
  width: 100%;
  max-width: 1512px;
  height: 568px;
  margin: 0 auto;
  overflow: hidden;
}

.col3-banner-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  display: block;
}

.col3-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.4);
}

.col3-button-grid {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.75rem 2.5rem;
  z-index: 10;
  width: 90%;
  max-width: 920px;
}

.col3-btn {
  background-color: #ffffff;
  border: none;
  border-radius: 6px;
  padding: 1.15rem 1.75rem;
  font-family: 'Montserrat', sans-serif;
  font-size: 32px;
  font-weight: 800;
  cursor: pointer;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.35);
  transition: all 0.25s ease;
  text-align: center;
  white-space: nowrap;
}

.col3-btn:hover {
  transform: translateY(-4px) scale(1.02);
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.45);
}

.col3-btn.btn-blue {
  color: #1d4ed8; /* Berwarna biru */
}

.col3-btn.btn-red {
  color: #e60012; /* Berwarna merah */
}

/* =========================================================
   KOLOM 4 STYLES (Mailing List)
   ========================================================= */
.hero-col-4 {
  width: 100%;
  background-color: #ffffff;
  padding: 5rem 2rem;
  box-sizing: border-box;
  text-align: center;
  border-top: 1px solid #f1f5f9;
}

.col4-container {
  max-width: 860px;
  margin: 0 auto;
}

.col4-title {
  font-family: 'Montserrat', sans-serif;
  font-size: 42px;
  font-weight: 900;
  color: #e60012; /* Berwarna merah */
  line-height: 1.2;
  margin-bottom: 0.85rem;
  letter-spacing: -0.01em;
}

.col4-subtitle {
  font-size: 18px;
  font-weight: 500;
  color: #4b5563;
  margin-bottom: 2.25rem;
  line-height: 1.5;
}

.col4-form {
  max-width: 580px;
  margin: 0 auto;
}

.email-input-wrapper {
  display: flex;
  align-items: center;
  background: #ffffff;
  border: 2px solid #e2e8f0;
  border-radius: 6px;
  padding: 4px;
  box-shadow: 0 4px 14px rgba(0, 0, 0, 0.05);
  transition: border-color 0.2s ease;
}

.email-input-wrapper:focus-within {
  border-color: #e60012;
}

.email-input-field {
  flex: 1;
  border: none;
  outline: none;
  font-size: 1rem;
  padding: 0.85rem 1.25rem;
  color: #1e293b;
  font-family: inherit;
}

.email-submit-btn {
  background-color: #e60012;
  color: #ffffff;
  border: none;
  border-radius: 4px;
  font-family: 'Montserrat', sans-serif;
  font-size: 0.9rem;
  font-weight: 800;
  letter-spacing: 0.06em;
  padding: 0.85rem 1.75rem;
  cursor: pointer;
  transition: background 0.2s ease;
  flex-shrink: 0;
}

.email-submit-btn:hover {
  background-color: #c4000f;
}

.success-message {
  margin-top: 1rem;
  color: #16a34a;
  font-weight: 600;
  font-size: 0.95rem;
}

/* =========================================================
   RESPONSIVE DESIGN
   ========================================================= */
@media (max-width: 1024px) {
  .col1-container {
    flex-direction: column;
    text-align: center;
  }
  
  .col1-title {
    font-size: 48px;
  }
  
  .col1-description {
    font-size: 22px;
  }

  .col1-actions {
    justify-content: center;
  }

  .col2-container {
    flex-direction: column;
    text-align: center;
  }

  .col3-btn {
    font-size: 24px;
    padding: 1rem 1.25rem;
  }
}

@media (max-width: 768px) {
  .col1-title {
    font-size: 36px;
  }

  .col1-description {
    font-size: 18px;
  }

  .col2-title {
    font-size: 26px;
  }

  .col2-paragraph {
    font-size: 16px;
  }

  .col3-banner-container {
    height: 480px;
  }

  .col3-button-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }

  .col3-btn {
    font-size: 20px;
    padding: 0.75rem 1rem;
  }

  .col4-title {
    font-size: 32px;
  }

  .email-input-wrapper {
    flex-direction: column;
    border: none;
    box-shadow: none;
    gap: 0.75rem;
  }

  .email-input-field {
    width: 100%;
    border: 2px solid #e2e8f0;
    border-radius: 6px;
  }

  .email-submit-btn {
    width: 100%;
  }
}
</style>

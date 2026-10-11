<script setup>
// Footer component for Yuji Nishida site
</script>

<template>
  <footer class="site-footer">
    <div class="footer-container">
      <!-- Main Content Section (Logo + 4 Columns) -->
      <div class="footer-main">
        <!-- Logo di sebelah kiri (Ukuran 170x170) -->
        <div class="footer-logo-wrapper">
          <a href="#" class="footer-brand-logo" aria-label="Train With Nishida">
            <div class="avatar-ring-large">
              <img 
                src="/nishida.jpg" 
                alt="Yuji Nishida" 
                class="avatar-img-large"
              />
            </div>
            <div class="brand-text-large">
              <span class="text-train-large">TRAIN WITH</span>
              <span class="text-nishida-large">NISHIDA</span>
            </div>
          </a>
        </div>

        <!-- Kolom 1: Programms -->
        <div class="footer-col">
          <h3 class="col-heading">Programms</h3>
          <ul class="col-list">
            <li><a href="#" class="col-link">Online Coaching</a></li>
            <li><a href="#" class="col-link">One to One</a></li>
            <li><a href="#" class="col-link">Elite Programms</a></li>
          </ul>
        </div>

        <!-- Kolom 2: Help -->
        <div class="footer-col">
          <h3 class="col-heading">Help</h3>
          <ul class="col-list">
            <li><a href="#" class="col-link">Privacy Policy</a></li>
            <li><a href="#" class="col-link">Terms of Service</a></li>
            <li><a href="#" class="col-link">Cookies</a></li>
          </ul>
        </div>

        <!-- Kolom 3: Contact -->
        <div class="footer-col">
          <h3 class="col-heading">Contact</h3>
          <ul class="col-list">
            <li><a href="#" class="col-link">Twitter</a></li>
            <li><a href="#" class="col-link">Facebook</a></li>
            <li><a href="#" class="col-link">Instagram</a></li>
            <li><a href="#" class="col-link">Linked in</a></li>
          </ul>
        </div>

        <!-- Kolom 4: Location -->
        <div class="footer-col">
          <h3 class="col-heading">Location</h3>
          <ul class="col-list">
            <li class="location-item">Osaka, Japan</li>
          </ul>
        </div>
      </div>

      <!-- Garis Putih Pemisah di Bawah Logo & Tulisan -->
      <div class="footer-divider"></div>

      <!-- Bagian Copyright di Bawah Garis Putih -->
      <div class="footer-bottom">
        <p class="copyright-text">
          @copyright 2024 all right reserved by Yuji Nishida
        </p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,600;0,700;0,800;0,900;1,800&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap');

/* Warna dasar hitam */
.site-footer {
  width: 100%;
  background-color: #000000;
  color: #ffffff;
  padding: 4.5rem 2rem 2.5rem;
  box-sizing: border-box;
  font-family: 'Plus Jakarta Sans', sans-serif;
  border-top: 1px solid #1a1a1a;
}

.footer-container {
  max-width: 1400px;
  margin: 0 auto;
  box-sizing: border-box;
}

/* Bagian Atas: Logo (170x170) dan 4 Kolom Menu */
.footer-main {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 3rem;
  flex-wrap: wrap;
  padding-bottom: 3.5rem;
}

/* Logo 170x170 */
.footer-logo-wrapper {
  width: 170px;
  height: 170px;
  flex-shrink: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.footer-brand-logo {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  gap: 0.65rem;
  width: 100%;
  height: 100%;
}

.avatar-ring-large {
  width: 105px;
  height: 105px;
  border-radius: 50%;
  padding: 3.5px;
  background: linear-gradient(135deg, #e60012, #333333);
  box-shadow: 0 4px 16px rgba(230, 0, 18, 0.4);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.3s ease;
}

.footer-brand-logo:hover .avatar-ring-large {
  transform: scale(1.05);
}

.avatar-img-large {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #ffffff;
  background-color: #1a1a1a;
}

.brand-text-large {
  display: flex;
  flex-direction: column;
  align-items: center;
  line-height: 1.1;
  font-family: 'Montserrat', sans-serif;
}

.text-train-large {
  background: #ffffff;
  color: #000000;
  padding: 1px 6px;
  border-radius: 3px;
  font-size: 0.7rem;
  font-weight: 800;
  letter-spacing: 0.12em;
  margin-bottom: 2px;
}

.text-nishida-large {
  font-size: 1.15rem;
  font-weight: 900;
  color: #e60012;
  letter-spacing: 0.04em;
  text-transform: uppercase;
}

/* Kolom Menu Styling */
.footer-col {
  display: flex;
  flex-direction: column;
}

/* Judul kolom: Ukuran font 32 */
.col-heading {
  font-family: 'Montserrat', sans-serif;
  font-size: 32px;
  font-weight: 800;
  color: #ffffff;
  margin: 0 0 1.5rem 0;
  line-height: 1.2;
}

.col-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.95rem;
}

/* Isi baris tulisan: Ukuran font 20 */
.col-link,
.location-item {
  font-size: 20px;
  color: #e2e8f0;
  text-decoration: none;
  line-height: 1.4;
  transition: color 0.2s ease, transform 0.2s ease;
  display: inline-block;
}

.col-link:hover {
  color: #e60012;
  transform: translateX(3px);
}

.location-item {
  color: #ffffff;
}

/* Garis Putih di bawah tulisan & logo */
.footer-divider {
  width: 100%;
  height: 1.5px;
  background-color: #ffffff;
  opacity: 0.9;
  margin: 0 0 2rem 0;
}

/* Bagian copyright */
.footer-bottom {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

/* Font ukuran 25 */
.copyright-text {
  font-size: 25px;
  font-weight: 500;
  color: #ffffff;
  margin: 0;
  line-height: 1.4;
  letter-spacing: 0.01em;
}

/* Responsif */
@media (max-width: 1100px) {
  .footer-main {
    gap: 2.2rem;
  }

  .col-heading {
    font-size: 26px;
  }

  .col-link,
  .location-item {
    font-size: 18px;
  }

  .copyright-text {
    font-size: 20px;
  }
}

@media (max-width: 768px) {
  .footer-main {
    flex-direction: column;
    gap: 2rem;
  }

  .footer-logo-wrapper {
    margin-bottom: 1rem;
  }

  .copyright-text {
    font-size: 17px;
  }
}
</style>

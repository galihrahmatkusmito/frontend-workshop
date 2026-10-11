<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const navMenus = [
  { name: 'Home', href: '#home', active: true },
  { name: 'My Story', href: '#story', active: false },
  { name: 'Online coaching', href: '#online-coaching', active: false },
  { name: 'Elit Programms', href: '#elite-programmes', active: false },
  { name: 'One to One', href: '#one-to-one', active: false },
  { name: 'FAQ', href: '#faq', active: false }
]

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}
</script>

<template>
  <header class="navbar-header">
    <div class="nav-container">
      <!-- Left: Logo & Athlete Profile -->
      <a href="#" class="brand-logo" aria-label="Train With Nishida">
        <div class="avatar-ring">
          <img 
            src="/nishida.jpg" 
            alt="Yuji Nishida - Japan National Volleyball Team" 
            class="avatar-img"
          />
        </div>
        <div class="brand-text">
          <span class="text-train">TRAIN WITH</span>
          <span class="text-nishida">NISHIDA</span>
        </div>
      </a>

      <!-- Center: 6 Menu Navigation (Desktop) -->
      <nav class="nav-menu" aria-label="Main Navigation">
        <ul class="nav-list">
          <li v-for="menu in navMenus" :key="menu.name" class="nav-item">
            <a 
              :href="menu.href" 
              class="nav-link"
              :class="{ 'active': menu.active }"
            >
              {{ menu.name }}
            </a>
          </li>
        </ul>
      </nav>

      <!-- Right: Contact Button & Mobile Toggle -->
      <div class="header-actions">
        <a href="#contact" class="btn-contact">
          CONTACT
        </a>

        <!-- Mobile Menu Toggle Button -->
        <button 
          class="mobile-toggle" 
          @click="toggleMobileMenu" 
          :aria-expanded="isMobileMenuOpen"
          aria-label="Toggle navigation menu"
        >
          <span class="bar" :class="{ 'open': isMobileMenuOpen }"></span>
          <span class="bar" :class="{ 'open': isMobileMenuOpen }"></span>
          <span class="bar" :class="{ 'open': isMobileMenuOpen }"></span>
        </button>
      </div>
    </div>

    <!-- Mobile Drawer Navigation -->
    <transition name="drawer">
      <div v-if="isMobileMenuOpen" class="mobile-drawer">
        <ul class="mobile-list">
          <li v-for="menu in navMenus" :key="menu.name" class="mobile-item">
            <a 
              :href="menu.href" 
              class="mobile-link"
              :class="{ 'active': menu.active }"
              @click="isMobileMenuOpen = false"
            >
              {{ menu.name }}
            </a>
          </li>
          <li class="mobile-item mobile-contact-wrapper">
            <a 
              href="#contact" 
              class="btn-contact btn-mobile" 
              @click="isMobileMenuOpen = false"
            >
              CONTACT
            </a>
          </li>
        </ul>
      </div>
    </transition>
  </header>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,600;0,700;0,800;0,900;1,800&family=Plus+Jakarta+Sans:wght@500;600;700&display=swap');

/* Header Base Styling */
.navbar-header {
  position: sticky;
  top: 0;
  left: 0;
  width: 100%;
  box-sizing: border-box;
  background-color: #ffffff;
  color: #111111;
  box-shadow: 0 4px 20px -2px rgba(0, 0, 0, 0.06);
  z-index: 1000;
  border-bottom: 1px solid rgba(0, 0, 0, 0.05);
  font-family: 'Plus Jakarta Sans', sans-serif;
  transition: all 0.3s ease;
}

.nav-container {
  width: 100%;
  max-width: 100%;
  margin: 0;
  box-sizing: border-box;
  padding: 0.85rem 3rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1.5rem;
}

/* Brand Logo (Left) */
.brand-logo {
  display: flex;
  align-items: center;
  gap: 0.85rem;
  text-decoration: none;
  flex-shrink: 0;
  user-select: none;
}

.avatar-ring {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  padding: 2.5px;
  background: linear-gradient(135deg, #e60012, #1a1a1a);
  box-shadow: 0 3px 10px rgba(230, 0, 18, 0.35);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.brand-logo:hover .avatar-ring {
  transform: scale(1.08) rotate(3deg);
}

.avatar-img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  background-color: #f0f0f0;
  border: 1.5px solid #ffffff;
}

.brand-text {
  display: flex;
  flex-direction: column;
  line-height: 1.05;
  font-family: 'Montserrat', sans-serif;
  letter-spacing: -0.01em;
}

.text-train {
  background: #111111;
  color: #ffffff;
  padding: 2px 6px;
  border-radius: 3px;
  font-size: 0.72rem;
  font-weight: 800;
  letter-spacing: 0.14em;
  display: inline-block;
  margin-bottom: 2px;
  width: fit-content;
}

.text-nishida {
  font-size: 1.25rem;
  font-weight: 900;
  color: #e60012; /* Merah timnas/Nishida */
  letter-spacing: 0.05em;
  text-transform: uppercase;
}

/* Center Navigation (6 Menu) */
.nav-menu {
  display: flex;
  align-items: center;
  justify-content: center;
}

.nav-list {
  display: flex;
  align-items: center;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 1.75rem;
}

.nav-item {
  position: relative;
}

.nav-link {
  text-decoration: none;
  font-size: 0.95rem;
  font-weight: 600;
  color: #2b2b2b;
  padding: 0.5rem 0.15rem;
  transition: color 0.25s ease;
  position: relative;
  display: inline-block;
  white-space: nowrap;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 2.5px;
  background-color: #e60012;
  border-radius: 2px;
  transition: width 0.25s ease, left 0.25s ease;
}

.nav-link:hover,
.nav-link.active {
  color: #e60012;
}

.nav-link:hover::after,
.nav-link.active::after {
  width: 100%;
  left: 0;
}

/* Right Section: Contact Button */
.header-actions {
  display: flex;
  align-items: center;
  gap: 1rem;
  flex-shrink: 0;
}

.btn-contact {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background-color: #e60012;
  color: #ffffff;
  font-family: 'Montserrat', sans-serif;
  font-size: 0.9rem;
  font-weight: 800;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  text-decoration: none;
  padding: 0.7rem 1.6rem;
  box-sizing: border-box;
  flex-shrink: 0;
  border-radius: 4px; /* Persegi panjang yang modern */
  border: 1.5px solid #e60012;
  box-shadow: 0 4px 12px rgba(230, 0, 18, 0.3);
  transition: background-color 0.2s ease, border-color 0.2s ease, box-shadow 0.2s ease;
  cursor: pointer;
  white-space: nowrap;
}

.btn-contact:hover {
  background-color: #c4000f;
  border-color: #c4000f;
  box-shadow: 0 4px 16px rgba(230, 0, 18, 0.45);
}

.btn-contact:active {
  background-color: #a3000c;
}

/* Mobile Toggle Hamburger */
.mobile-toggle {
  display: none;
  flex-direction: column;
  justify-content: space-around;
  width: 32px;
  height: 26px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
}

.mobile-toggle .bar {
  width: 100%;
  height: 3px;
  background-color: #1a1a1a;
  border-radius: 2px;
  transition: all 0.3s ease;
}

.mobile-toggle .bar.open:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
}

.mobile-toggle .bar.open:nth-child(2) {
  opacity: 0;
}

.mobile-toggle .bar.open:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

/* Mobile Drawer */
.mobile-drawer {
  background: #ffffff;
  border-top: 1px solid #f0f0f0;
  box-shadow: 0 10px 20px rgba(0,0,0,0.08);
  padding: 1.25rem 2rem;
}

.mobile-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.mobile-link {
  display: block;
  text-decoration: none;
  font-size: 1.05rem;
  font-weight: 600;
  color: #222222;
  padding: 0.5rem 0;
  border-bottom: 1px solid #f5f5f5;
  transition: color 0.2s ease;
}

.mobile-link.active,
.mobile-link:hover {
  color: #e60012;
}

.mobile-contact-wrapper {
  padding-top: 0.5rem;
}

.btn-mobile {
  width: 100%;
  text-align: center;
}

/* Responsive Media Queries */
@media (max-width: 1100px) {
  .nav-list {
    gap: 1.15rem;
  }
  .nav-link {
    font-size: 0.88rem;
  }
}

@media (max-width: 950px) {
  .nav-menu {
    display: none;
  }

  .mobile-toggle {
    display: flex;
  }

  .btn-contact {
    display: none;
  }

  .btn-mobile {
    display: inline-flex;
  }
}
</style>

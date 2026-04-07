<template>
  <header class="navbar" :class="{ scrolled: isScrolled, hidden: isHidden }">
    <div class="container navbar-inner">
      <a href="#" class="logo">
        <span class="logo-symbol">&lt;</span>Daein<span class="logo-symbol">/&gt;</span>
      </a>

      <nav class="nav-links" :class="{ open: menuOpen }">
        <a
          v-for="link in navLinks"
          :key="link.id"
          :href="`#${link.id}`"
          class="nav-link"
          :class="{ active: activeSection === link.id }"
          @click="menuOpen = false"
        >
          {{ link.label }}
        </a>
      </nav>

      <button class="menu-toggle" @click="menuOpen = !menuOpen" :aria-label="menuOpen ? '메뉴 닫기' : '메뉴 열기'">
        <span class="bar" :class="{ open: menuOpen }"></span>
      </button>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const navLinks = [
  { id: 'about', label: 'About' },
  { id: 'skills', label: 'Skills' },
  { id: 'projects', label: 'Projects' },
  { id: 'experience', label: 'Experience' },
  { id: 'contact', label: 'Contact' },
];

const isScrolled = ref(false);
const isHidden = ref(false);
const menuOpen = ref(false);
const activeSection = ref('');
let lastScrollY = 0;

function handleScroll() {
  const y = window.scrollY;
  isScrolled.value = y > 40;
  isHidden.value = y > lastScrollY && y > 400;
  lastScrollY = y;

  const sections = navLinks.map(l => document.getElementById(l.id)).filter(Boolean);
  for (let i = sections.length - 1; i >= 0; i--) {
    if (sections[i].getBoundingClientRect().top <= 120) {
      activeSection.value = navLinks[i].id;
      return;
    }
  }
  activeSection.value = '';
}

onMounted(() => window.addEventListener('scroll', handleScroll, { passive: true }));
onUnmounted(() => window.removeEventListener('scroll', handleScroll));
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 20px 0;
  transition: all var(--transition-base);
}

.navbar.scrolled {
  padding: 12px 0;
  background: rgba(10, 10, 15, 0.85);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--color-border);
}

.navbar.hidden {
  transform: translateY(-100%);
}

.navbar-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-size: 1.3rem;
  font-weight: 700;
  letter-spacing: -0.5px;
}

.logo-symbol {
  color: var(--color-primary);
}

.nav-links {
  display: flex;
  gap: 8px;
}

.nav-link {
  padding: 8px 16px;
  font-size: 0.9rem;
  font-weight: 400;
  color: var(--color-text-secondary);
  border-radius: 8px;
  transition: all var(--transition-base);
}

.nav-link:hover,
.nav-link.active {
  color: var(--color-text);
  background: rgba(108, 99, 255, 0.1);
}

.nav-link.active {
  color: var(--color-primary-light);
}

.menu-toggle {
  display: none;
  width: 32px;
  height: 32px;
  align-items: center;
  justify-content: center;
}

.bar,
.bar::before,
.bar::after {
  display: block;
  width: 22px;
  height: 2px;
  background: var(--color-text);
  border-radius: 2px;
  transition: all var(--transition-base);
  position: relative;
}

.bar::before,
.bar::after {
  content: '';
  position: absolute;
}

.bar::before { top: -7px; }
.bar::after { top: 7px; }

.bar.open {
  background: transparent;
}

.bar.open::before {
  top: 0;
  transform: rotate(45deg);
}

.bar.open::after {
  top: 0;
  transform: rotate(-45deg);
}

@media (max-width: 768px) {
  .menu-toggle {
    display: flex;
  }

  .nav-links {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(10, 10, 15, 0.97);
    backdrop-filter: blur(20px);
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 8px;
    opacity: 0;
    pointer-events: none;
    transition: opacity var(--transition-base);
  }

  .nav-links.open {
    opacity: 1;
    pointer-events: all;
  }

  .nav-link {
    font-size: 1.2rem;
    padding: 14px 32px;
  }
}
</style>

<template>
  <footer class="footer">
    <div class="container footer-inner">
      <p class="footer-copyright">
        &copy; {{ currentYear }} 조대인. All rights reserved.
      </p>
      <p class="footer-built">
        Built with <span class="heart">Vue.js</span> &amp; <span class="heart">Vite</span>
      </p>
    </div>
  </footer>
</template>

<script setup>
const currentYear = new Date().getFullYear();
</script>

<style scoped>
.footer {
  border-top: 1px solid var(--color-border);
  padding: 32px 0;
}

.footer-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.footer-copyright {
  font-size: 0.85rem;
  color: var(--color-text-muted);
}

.footer-built {
  font-size: 0.85rem;
  color: var(--color-text-muted);
}

.heart {
  color: var(--color-primary-light);
  font-weight: 500;
}

@media (max-width: 768px) {
  .footer-inner {
    flex-direction: column;
    gap: 8px;
    text-align: center;
  }
}
</style>

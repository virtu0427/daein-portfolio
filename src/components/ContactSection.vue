<template>
  <section id="contact" class="section">
    <div class="container">
      <div class="contact-inner">
        <div class="section-header">
          <span class="section-label">Contact</span>
          <h2 class="section-title">연락하기</h2>
          <p class="section-desc">
            함께 일하고 싶거나 궁금한 점이 있다면 편하게 연락해주세요.
          </p>
        </div>

        <div class="contact-grid">
          <a
            v-for="link in contactLinks"
            :key="link.label"
            :href="link.href"
            target="_blank"
            rel="noopener"
            class="contact-card card"
          >
            <span class="contact-icon">{{ link.icon }}</span>
            <h3 class="contact-label">{{ link.label }}</h3>
            <p class="contact-value">{{ link.value }}</p>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
/* 아래 연락처 정보를 본인에 맞게 수정하세요 */
const contactLinks = [
  {
    icon: '📧',
    label: 'Email',
    value: 'your-email@example.com',
    href: 'mailto:your-email@example.com',
  },
  {
    icon: '💻',
    label: 'GitHub',
    value: 'github.com/username',
    href: 'https://github.com/username',
  },
  {
    icon: '💼',
    label: 'LinkedIn',
    value: 'linkedin.com/in/username',
    href: 'https://linkedin.com/in/username',
  },
  {
    icon: '📝',
    label: 'Blog',
    value: 'blog-url.com',
    href: 'https://blog-url.com',
  },
];
</script>

<style scoped>
.contact-inner {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.contact-inner .section-header {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.contact-inner .section-desc {
  margin: 0 auto;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}

.contact-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  text-align: center;
  cursor: pointer;
}

.contact-icon {
  font-size: 2rem;
  width: 56px;
  height: 56px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(108, 99, 255, 0.08);
  border-radius: 50%;
}

.contact-label {
  font-size: 1rem;
  font-weight: 600;
  color: var(--color-text);
}

.contact-value {
  font-size: 0.88rem;
  color: var(--color-text-secondary);
}

@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
  }
}
</style>

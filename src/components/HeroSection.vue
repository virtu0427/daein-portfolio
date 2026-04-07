<template>
  <section class="hero">
    <div class="hero-bg">
      <div class="grid-overlay"></div>
      <div class="glow glow-1"></div>
      <div class="glow glow-2"></div>
    </div>

    <div class="container hero-content">
      <p class="hero-greeting fade-in-up">안녕하세요, 저는</p>
      <h1 class="hero-name fade-in-up" style="animation-delay: 0.1s">
        조대인<span class="dot">.</span>
      </h1>
      <h2 class="hero-tagline fade-in-up" style="animation-delay: 0.2s">
        <!-- 아래 문구를 본인 역할에 맞게 수정하세요 -->
        문제를 해결하는 개발자
      </h2>
      <p class="hero-desc fade-in-up" style="animation-delay: 0.3s">
        <!-- 아래 소개 문구를 수정하세요 -->
        보안과 개발을 아우르며, 기술로 더 안전하고 편리한 세상을 만들어갑니다.
      </p>
      <div class="hero-actions fade-in-up" style="animation-delay: 0.4s">
        <a href="#projects" class="btn btn-primary">프로젝트 보기</a>
        <a href="#contact" class="btn btn-outline">연락하기</a>
      </div>

      <div class="hero-scroll fade-in-up" style="animation-delay: 0.6s">
        <div class="scroll-indicator">
          <div class="scroll-dot"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: 0;
  pointer-events: none;
}

.grid-overlay {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(108, 99, 255, 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(108, 99, 255, 0.03) 1px, transparent 1px);
  background-size: 60px 60px;
}

.glow {
  position: absolute;
  border-radius: 50%;
  filter: blur(120px);
  opacity: 0.4;
}

.glow-1 {
  width: 500px;
  height: 500px;
  background: var(--color-primary);
  top: -150px;
  right: -100px;
  opacity: 0.12;
}

.glow-2 {
  width: 400px;
  height: 400px;
  background: var(--color-accent);
  bottom: -100px;
  left: -100px;
  opacity: 0.08;
}

.hero-content {
  position: relative;
  z-index: 1;
  padding-top: 120px;
  padding-bottom: 80px;
}

.hero-greeting {
  font-size: 1.1rem;
  color: var(--color-primary-light);
  font-weight: 500;
  margin-bottom: 16px;
}

.hero-name {
  font-size: clamp(2.8rem, 8vw, 5rem);
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 12px;
  letter-spacing: -2px;
}

.dot {
  color: var(--color-primary);
}

.hero-tagline {
  font-size: clamp(1.3rem, 3vw, 2rem);
  font-weight: 400;
  color: var(--color-text-secondary);
  margin-bottom: 24px;
}

.hero-desc {
  font-size: 1.1rem;
  color: var(--color-text-muted);
  max-width: 520px;
  line-height: 1.8;
  margin-bottom: 40px;
}

.hero-actions {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

.hero-scroll {
  position: absolute;
  bottom: 40px;
  left: 50%;
  transform: translateX(-50%);
}

.scroll-indicator {
  width: 24px;
  height: 40px;
  border: 2px solid var(--color-border-light);
  border-radius: 12px;
  display: flex;
  justify-content: center;
  padding-top: 8px;
}

.scroll-dot {
  width: 4px;
  height: 8px;
  background: var(--color-primary-light);
  border-radius: 4px;
  animation: scrollBounce 2s ease-in-out infinite;
}

@keyframes scrollBounce {
  0%, 100% { transform: translateY(0); opacity: 1; }
  50% { transform: translateY(10px); opacity: 0.3; }
}
</style>

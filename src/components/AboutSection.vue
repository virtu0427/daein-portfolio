<template>
  <section id="about" class="section">
    <div class="container">
      <div class="section-header">
        <span class="section-label">About Me</span>
        <h2 class="section-title">저를 소개합니다</h2>
      </div>

      <div class="about-grid">
        <div class="about-photo">
          <div class="photo-frame">
            <!-- 프로필 이미지를 public/profile.jpg에 넣고 경로를 수정하세요 -->
            <div class="photo-placeholder">
              <span>📷</span>
              <p>프로필 사진</p>
            </div>
          </div>
        </div>

        <div class="about-text">
          <p class="about-intro">
            <!-- 아래 자기소개를 수정하세요 -->
            안녕하세요! 저는 기술에 대한 열정을 가진 개발자 <strong>조대인</strong>입니다.
            새로운 기술을 배우고 실무에 적용하는 것을 즐기며,
            팀원들과 함께 성장하는 것을 중요하게 생각합니다.
          </p>
          <p class="about-detail">
            <!-- 추가 소개글을 작성하세요 -->
            보안과 소프트웨어 개발의 교차점에서 더 나은 솔루션을 만들기 위해 끊임없이 도전합니다.
          </p>

          <div class="about-info">
            <div class="info-item" v-for="item in infoItems" :key="item.label">
              <span class="info-label">{{ item.label }}</span>
              <span class="info-value">{{ item.value }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const infoItems = [
  { label: '이름', value: '조대인' },
  { label: '이메일', value: 'your-email@example.com' },
  { label: '위치', value: '대한민국' },
  { label: '학력', value: 'OO대학교 OO학과' },
];
</script>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 300px 1fr;
  gap: 60px;
  align-items: start;
}

.photo-frame {
  aspect-ratio: 1;
  border-radius: var(--radius-lg);
  overflow: hidden;
  border: 2px solid var(--color-border);
  background: var(--color-bg-card);
  position: relative;
}

.photo-frame::after {
  content: '';
  position: absolute;
  inset: -8px;
  border: 2px solid var(--color-primary);
  border-radius: calc(var(--radius-lg) + 4px);
  opacity: 0.2;
  z-index: -1;
}

.photo-placeholder {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 8px;
  color: var(--color-text-muted);
  font-size: 0.9rem;
}

.photo-placeholder span {
  font-size: 2.5rem;
}

.about-intro {
  font-size: 1.1rem;
  line-height: 1.9;
  color: var(--color-text);
  margin-bottom: 16px;
}

.about-intro strong {
  color: var(--color-primary-light);
}

.about-detail {
  font-size: 1rem;
  color: var(--color-text-secondary);
  line-height: 1.8;
  margin-bottom: 32px;
}

.about-info {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}

.info-item {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.info-label {
  font-size: 0.8rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: var(--color-text-muted);
}

.info-value {
  font-size: 1rem;
  color: var(--color-text);
}

@media (max-width: 768px) {
  .about-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .photo-frame {
    max-width: 250px;
    margin: 0 auto;
  }

  .about-info {
    grid-template-columns: 1fr;
  }
}
</style>

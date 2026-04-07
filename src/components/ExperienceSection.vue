<template>
  <section id="experience" class="section">
    <div class="container">
      <div class="section-header">
        <span class="section-label">Experience</span>
        <h2 class="section-title">경험 & 이력</h2>
        <p class="section-desc">성장 과정과 주요 경험을 소개합니다.</p>
      </div>

      <div class="timeline">
        <div
          class="timeline-item"
          v-for="(item, index) in experiences"
          :key="index"
          :class="{ 'item-right': index % 2 !== 0 }"
        >
          <div class="timeline-dot"></div>
          <div class="timeline-card card">
            <span class="timeline-period">{{ item.period }}</span>
            <h3 class="timeline-title">{{ item.title }}</h3>
            <p class="timeline-org">{{ item.organization }}</p>
            <p class="timeline-desc">{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
/* 아래 경험/이력 데이터를 본인에 맞게 수정하세요 */
const experiences = [
  {
    period: '2024 - 현재',
    title: '직무 / 역할',
    organization: '회사 또는 기관명',
    description: '담당 업무와 성과에 대한 간단한 설명을 작성하세요.',
  },
  {
    period: '2023 - 2024',
    title: '인턴십 / 프로젝트',
    organization: '회사 또는 기관명',
    description: '담당 업무와 성과에 대한 간단한 설명을 작성하세요.',
  },
  {
    period: '2021 - 2023',
    title: '동아리 / 스터디 활동',
    organization: '활동 기관명',
    description: '참여한 활동과 배운 점에 대해 작성하세요.',
  },
  {
    period: '2020 - 현재',
    title: 'OO학과 재학',
    organization: 'OO대학교',
    description: '전공 관련 학습 내용이나 성과를 작성하세요.',
  },
];
</script>

<style scoped>
.timeline {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
  padding-left: 40px;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 15px;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(
    to bottom,
    var(--color-primary) 0%,
    var(--color-border) 100%
  );
}

.timeline-item {
  position: relative;
  margin-bottom: 32px;
}

.timeline-item:last-child {
  margin-bottom: 0;
}

.timeline-dot {
  position: absolute;
  left: -33px;
  top: 28px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: var(--color-primary);
  border: 3px solid var(--color-bg);
  box-shadow: 0 0 0 3px rgba(108, 99, 255, 0.3);
  z-index: 1;
}

.timeline-card {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.timeline-period {
  font-size: 0.82rem;
  font-weight: 600;
  color: var(--color-primary-light);
  letter-spacing: 0.5px;
}

.timeline-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--color-text);
}

.timeline-org {
  font-size: 0.92rem;
  color: var(--color-text-secondary);
}

.timeline-desc {
  font-size: 0.9rem;
  color: var(--color-text-muted);
  line-height: 1.7;
}

@media (max-width: 768px) {
  .timeline {
    padding-left: 32px;
  }

  .timeline-dot {
    left: -25px;
  }
}
</style>

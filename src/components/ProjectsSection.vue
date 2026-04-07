<template>
  <section id="projects" class="section">
    <div class="container">
      <div class="section-header">
        <span class="section-label">Projects</span>
        <h2 class="section-title">프로젝트</h2>
        <p class="section-desc">주요 프로젝트들을 소개합니다.</p>
      </div>

      <div class="projects-grid">
        <article class="project-card card" v-for="project in projects" :key="project.title">
          <div class="project-image">
            <div class="image-placeholder">
              <span>🖼️</span>
              <p>프로젝트 스크린샷</p>
            </div>
          </div>

          <div class="project-body">
            <div class="project-meta">
              <span class="project-type">{{ project.type }}</span>
              <span class="project-period">{{ project.period }}</span>
            </div>
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-desc">{{ project.description }}</p>

            <div class="project-tech">
              <span class="tag" v-for="tech in project.tech" :key="tech">{{ tech }}</span>
            </div>

            <div class="project-links">
              <a v-if="project.github" :href="project.github" target="_blank" rel="noopener" class="project-link">
                GitHub ↗
              </a>
              <a v-if="project.demo" :href="project.demo" target="_blank" rel="noopener" class="project-link">
                Demo ↗
              </a>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
/* 아래 프로젝트 데이터를 본인의 프로젝트로 수정하세요 */
const projects = [
  {
    title: '프로젝트 이름 1',
    type: '팀 프로젝트',
    period: '2025.01 - 2025.06',
    description:
      '프로젝트에 대한 간단한 설명을 작성하세요. 어떤 문제를 해결했는지, 주요 기능은 무엇인지 서술합니다.',
    tech: ['Vue.js', 'Node.js', 'MongoDB'],
    github: 'https://github.com/username/project1',
    demo: '',
  },
  {
    title: '프로젝트 이름 2',
    type: '개인 프로젝트',
    period: '2024.09 - 2024.12',
    description:
      '프로젝트에 대한 간단한 설명을 작성하세요. 어떤 문제를 해결했는지, 주요 기능은 무엇인지 서술합니다.',
    tech: ['Python', 'Flask', 'MySQL'],
    github: 'https://github.com/username/project2',
    demo: 'https://demo-url.com',
  },
  {
    title: '프로젝트 이름 3',
    type: '팀 프로젝트',
    period: '2024.03 - 2024.08',
    description:
      '프로젝트에 대한 간단한 설명을 작성하세요. 어떤 문제를 해결했는지, 주요 기능은 무엇인지 서술합니다.',
    tech: ['React', 'Spring Boot', 'PostgreSQL'],
    github: '',
    demo: '',
  },
];
</script>

<style scoped>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(360px, 1fr));
  gap: 28px;
}

.project-card {
  padding: 0;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.project-image {
  aspect-ratio: 16 / 9;
  background: var(--color-bg-secondary);
  border-bottom: 1px solid var(--color-border);
}

.image-placeholder {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 8px;
  color: var(--color-text-muted);
  font-size: 0.85rem;
}

.image-placeholder span {
  font-size: 2rem;
}

.project-body {
  padding: 24px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  flex: 1;
}

.project-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.project-type {
  font-size: 0.8rem;
  font-weight: 500;
  color: var(--color-primary-light);
}

.project-period {
  font-size: 0.78rem;
  color: var(--color-text-muted);
}

.project-title {
  font-size: 1.2rem;
  font-weight: 600;
  color: var(--color-text);
}

.project-desc {
  font-size: 0.92rem;
  color: var(--color-text-secondary);
  line-height: 1.7;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-top: 4px;
}

.project-links {
  display: flex;
  gap: 16px;
  margin-top: auto;
  padding-top: 8px;
}

.project-link {
  font-size: 0.88rem;
  font-weight: 500;
  color: var(--color-primary-light);
  transition: color var(--transition-base);
}

.project-link:hover {
  color: var(--color-accent);
}

@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>

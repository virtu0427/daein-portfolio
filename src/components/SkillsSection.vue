<template>
  <section id="skills" class="section">
    <div class="container">
      <div class="section-header">
        <span class="section-label">Skills</span>
        <h2 class="section-title">기술 스택</h2>
        <p class="section-desc">프로젝트에서 활용하는 기술들입니다.</p>
      </div>

      <div class="skills-grid">
        <div class="skill-category card" v-for="category in skillCategories" :key="category.title">
          <div class="category-icon">{{ category.icon }}</div>
          <h3 class="category-title">{{ category.title }}</h3>
          <div class="skill-tags">
            <span class="tag" v-for="skill in category.skills" :key="skill">{{ skill }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
/* 아래 카테고리와 스킬 목록을 본인에 맞게 수정하세요 */
const skillCategories = [
  {
    icon: '🖥️',
    title: 'Frontend',
    skills: ['HTML', 'CSS', 'JavaScript', 'Vue.js', 'React'],
  },
  {
    icon: '⚙️',
    title: 'Backend',
    skills: ['Node.js', 'Python', 'Java', 'Spring Boot', 'REST API'],
  },
  {
    icon: '🗄️',
    title: 'Database',
    skills: ['MySQL', 'PostgreSQL', 'MongoDB', 'Redis'],
  },
  {
    icon: '🔐',
    title: 'Security',
    skills: ['네트워크 보안', '침투 테스트', '취약점 분석', '포렌식'],
  },
  {
    icon: '🛠️',
    title: 'DevOps & Tools',
    skills: ['Git', 'Docker', 'Linux', 'AWS', 'CI/CD'],
  },
  {
    icon: '🤝',
    title: 'Collaboration',
    skills: ['Jira', 'Notion', 'Figma', 'Slack', 'Agile/Scrum'],
  },
];
</script>

<style scoped>
.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 24px;
}

.skill-category {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.category-icon {
  font-size: 2rem;
  width: 52px;
  height: 52px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(108, 99, 255, 0.08);
  border-radius: var(--radius-sm);
}

.category-title {
  font-size: 1.15rem;
  font-weight: 600;
  color: var(--color-text);
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
}
</style>

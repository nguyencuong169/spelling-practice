<template>
  <div id="app" class="app-container">
    <header class="app-header">
      <h1>{{ appTitle }}</h1>
      <p class="subtitle">{{ appSubtitle }}</p>
    </header>
    
    <main class="app-main">
      <component :is="currentComponent" @navigate="handleNavigation"></component>
    </main>
    
    <footer class="app-footer">
      <p>&copy; 2026 Spelling Practice. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
import { ref } from 'vue';
import HomePage from './components/HomePage.vue';
import QuizPage from './components/QuizPage.vue';

export default {
  name: 'App',
  components: {
    HomePage,
    QuizPage
  },
  setup() {
    const appTitle = 'Luyện Chính Tả';
    const appSubtitle = 'Ứng dụng luyện tập chính tả tiếng Việt cho bé';
    const currentComponent = ref('HomePage');

    const handleNavigation = (component) => {
      currentComponent.value = component;
    };

    return {
      appTitle,
      appSubtitle,
      currentComponent,
      handleNavigation
    };
  }
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.app-header {
  background-color: rgba(0, 0, 0, 0.2);
  color: white;
  padding: 2rem 1rem;
  text-align: center;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.app-header h1 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
  font-weight: bold;
}

.subtitle {
  font-size: 1.1rem;
  opacity: 0.9;
}

.app-main {
  flex: 1;
  padding: 2rem 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

.app-footer {
  background-color: rgba(0, 0, 0, 0.3);
  color: white;
  padding: 1rem;
  text-align: center;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .app-header h1 {
    font-size: 2rem;
  }
  
  .app-header {
    padding: 1.5rem 1rem;
  }
}
</style>
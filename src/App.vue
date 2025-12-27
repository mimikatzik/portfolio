<template>
  <div class="min-h-screen bg-black text-white">
    <section class="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div class="absolute inset-0 overflow-hidden">
        <div class="absolute top-20 left-10 w-72 h-72 bg-blue-500/10 rounded-full blur-3xl animate-pulse-slow"></div>
        <div class="absolute bottom-20 right-10 w-96 h-96 bg-purple-500/10 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 1s;"></div>
        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-cyan-500/5 rounded-full blur-3xl"></div>
      </div>

      <div class="relative z-10 container mx-auto px-4 sm:px-6 lg:px-8 text-center animate-fade-in">
        <div class="mb-6 animate-slide-up" style="animation-delay: 0.2s;">
          <h1 class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-bold mb-4">
            <span class="text-gradient">SOC L1 Аналитик</span>
          </h1>
        </div>
        <p class="text-lg sm:text-xl md:text-2xl text-gray-300 mb-8 max-w-2xl mx-auto animate-slide-up" style="animation-delay: 0.4s;">
          Начинающий специалист по кибербезопасности
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center items-center animate-slide-up" style="animation-delay: 0.6s;">
          <div class="w-2 h-2 bg-cyan-400 rounded-full animate-pulse"></div>
          <span class="text-gray-400">Ищу возможности для профессионального роста</span>
        </div>
      </div>

      <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
        <svg class="w-6 h-6 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
        </svg>
      </div>
    </section>

    <section id="about" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="container mx-auto max-w-4xl">
        <h2 class="text-3xl sm:text-4xl font-bold mb-12 text-center animate-slide-in-left">
          <span class="text-gradient">О себе</span>
        </h2>
        <div class="bg-gray-900/50 backdrop-blur-sm rounded-2xl p-6 sm:p-8 md:p-10 border border-gray-800 hover-glow animate-slide-up">
          <p class="text-gray-300 text-lg leading-relaxed mb-6">
            Начинающий аналитик SOC L1 с глубоким интересом к кибербезопасности и защите информационных систем. 
            Стремлюсь развивать навыки в области мониторинга безопасности, анализа инцидентов и реагирования на угрозы.
          </p>
          <p class="text-gray-300 text-lg leading-relaxed">
            Готов к обучению и работе в команде профессионалов, где смогу применить свои знания и получить 
            ценный опыт в сфере информационной безопасности.
          </p>
        </div>
      </div>
    </section>

    <section id="skills" class="py-20 px-4 sm:px-6 lg:px-8 bg-gray-950/50">
      <div class="container mx-auto max-w-6xl">
        <h2 class="text-3xl sm:text-4xl font-bold mb-12 text-center animate-slide-in-right">
          <span class="text-gradient">Навыки</span>
        </h2>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <div 
            v-for="(skill, index) in skills" 
            :key="index"
            class="bg-gray-900/50 backdrop-blur-sm rounded-xl p-6 border border-gray-800 hover:border-cyan-500/50 transition-all duration-300 hover-glow animate-slide-up"
            :style="`animation-delay: ${index * 0.1}s`"
          >
            <div class="flex items-center mb-4">
              <div class="w-12 h-12 bg-gradient-to-br from-cyan-500 to-blue-500 rounded-lg flex items-center justify-center mr-4">
                <span class="text-2xl">{{ skill.icon }}</span>
              </div>
              <h3 class="text-xl font-semibold">{{ skill.title }}</h3>
            </div>
            <p class="text-gray-400">{{ skill.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <section id="experience" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="container mx-auto max-w-4xl">
        <h2 class="text-3xl sm:text-4xl font-bold mb-12 text-center animate-slide-in-left">
          <span class="text-gradient">Опыт и образование</span>
        </h2>
        <div class="space-y-8">
          <div 
            v-for="(item, index) in experience" 
            :key="index"
            class="bg-gray-900/50 backdrop-blur-sm rounded-xl p-6 sm:p-8 border border-gray-800 hover-glow animate-slide-up"
            :style="`animation-delay: ${index * 0.15}s`"
          >
            <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between mb-4">
              <h3 class="text-xl sm:text-2xl font-semibold text-cyan-400 mb-2 sm:mb-0">{{ item.title }}</h3>
              <span class="text-gray-400 text-sm sm:text-base">{{ item.period }}</span>
            </div>
            <p class="text-gray-300 mb-3">{{ item.organization }}</p>
            <ul class="list-disc list-inside space-y-2 text-gray-400">
              <li v-for="(point, idx) in item.points" :key="idx">{{ point }}</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section id="contacts" class="py-20 px-4 sm:px-6 lg:px-8 bg-gray-950/50">
      <div class="container mx-auto max-w-4xl">
        <h2 class="text-3xl sm:text-4xl font-bold mb-12 text-center animate-slide-in-right">
          <span class="text-gradient">Контакты</span>
        </h2>
        <div class="grid grid-cols-1 sm:grid-cols-3 gap-6">
          <a 
            v-for="(contact, index) in contacts" 
            :key="index"
            :href="contact.link"
            target="_blank"
            rel="noopener noreferrer"
            class="bg-gray-900/50 backdrop-blur-sm rounded-xl p-6 border border-gray-800 hover:border-cyan-500/50 transition-all duration-300 hover-glow group animate-slide-up"
            :style="`animation-delay: ${index * 0.1}s`"
          >
            <div class="flex flex-col items-center text-center">
              <div class="w-16 h-16 bg-gradient-to-br from-cyan-500 to-blue-500 rounded-full flex items-center justify-center mb-4 group-hover:scale-110 transition-transform duration-300">
                <span class="text-3xl">{{ contact.icon }}</span>
              </div>
              <h3 class="text-lg font-semibold mb-2">{{ contact.title }}</h3>
              <p class="text-gray-400 text-sm break-all">{{ contact.value }}</p>
            </div>
          </a>
        </div>
      </div>
    </section>

    <footer class="py-8 px-4 text-center border-t border-gray-800">
      <p class="text-gray-500 text-sm">
        © {{ new Date().getFullYear() }} SOC L1 Аналитик. Все права защищены.
      </p>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const skills = ref([
  {
    icon: '🔍',
    title: 'Мониторинг безопасности',
    description: 'Базовые навыки работы с SIEM системами и мониторингом событий безопасности'
  },
  {
    icon: '🛡️',
    title: 'Анализ угроз',
    description: 'Понимание основных типов киберугроз и методов их обнаружения'
  },
  {
    icon: '📊',
    title: 'Анализ логов',
    description: 'Работа с логами различных систем и выявление аномалий'
  },
  {
    icon: '🔐',
    title: 'Основы сетевой безопасности',
    description: 'Знание протоколов, сетевых атак и методов защиты'
  },
  {
    icon: '💻',
    title: 'Инструменты безопасности',
    description: 'Ознакомление с популярными инструментами кибербезопасности'
  },
  {
    icon: '📚',
    title: 'Непрерывное обучение',
    description: 'Активное изучение новых технологий и практик в области SOC'
  }
])

const experience = ref([
  {
    title: 'Обучение и саморазвитие',
    organization: 'Самостоятельное изучение',
    period: '2024 - настоящее время',
    points: [
      'Изучение основ кибербезопасности и работы SOC',
      'Прохождение онлайн-курсов по информационной безопасности',
      'Изучение SIEM систем и методов анализа инцидентов',
      'Практика на платформах для обучения кибербезопасности'
    ]
  },
  {
    title: 'Базовое образование',
    organization: 'IT / Кибербезопасность',
    period: '2023 - 2024',
    points: [
      'Изучение основ информационной безопасности',
      'Знакомство с сетевыми технологиями',
      'Основы работы с Linux и Windows системами'
    ]
  }
])

const contacts = ref([
  {
    icon: '📧',
    title: 'Email',
    value: 'your.email@example.com',
    link: 'mailto:your.email@example.com'
  },
  {
    icon: '📱',
    title: 'Telegram',
    value: '@your_telegram',
    link: 'https://t.me/your_telegram'
  },
  {
    icon: '☎️',
    title: 'Телефон',
    value: '+7 (XXX) XXX-XX-XX',
    link: 'tel:+7XXXXXXXXXX'
  }
])
</script>

<style scoped>
html {
  scroll-behavior: smooth;
}
</style>


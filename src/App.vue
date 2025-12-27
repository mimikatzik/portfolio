<template>
  <div class="min-h-screen bg-black text-white">
    <section class="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div class="absolute inset-0 overflow-hidden">
        <div class="absolute top-20 left-10 w-72 h-72 bg-emerald-500/10 rounded-full blur-3xl animate-pulse-slow"></div>
        <div class="absolute bottom-20 right-10 w-96 h-96 bg-green-500/10 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 1s;"></div>
        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-green-400/5 rounded-full blur-3xl"></div>
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
        <div class="bg-gradient-to-br from-black to-green-950/50 border border-green-800/50 p-9 space-y-6 rounded-2xl shadow-2xl hover-glow animate-slide-up">
          <p class="text-gray-300 text-lg leading-relaxed mb-6">
            Начинающий аналитик SOC L1, ориентированный на мониторинг и первичный анализ инцидентов информационной безопасности. Имею практический опыт работы с логами, SIEM (Splunk, Elastic Stack), IDS/IPS (Snort), а также анализа сетевого трафика с использованием Wireshark. Уверенный пользователь ОС Linux и Windows, понимаю сетевые протоколы и типовые сценарии атак.
          </p>
          <p class="text-gray-300 text-lg leading-relaxed mb-6">
            Прохожу профильное обучение и практику на платформах TryHackMe и Hack The Box. Принимала участие в CTF. 
          </p>
          <p class="text-gray-300 text-lg leading-relaxed">
            Комфортно работаю с рутиной, придерживаюсь плейбуков и регламентов SOC, своевременно эскалирую инциденты и аккуратно оформляю результаты анализа. Легко и с желанием обучаюсь, к работе подхожу ответственно.
          </p>
        </div>
      </div>
    </section>

    <section id="skills" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="container mx-auto max-w-6xl">
        <h2 class="text-3xl sm:text-4xl font-bold mb-12 text-center animate-slide-in-right">
          <span class="text-gradient">Навыки</span>
        </h2>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <div 
            v-for="(skill, index) in skills" 
            :key="index"
            class="bg-gradient-to-br from-black to-green-950/50 border border-green-800/50 p-6 space-y-6 rounded-2xl shadow-2xl hover-glow animate-slide-up"
            :style="`animation-delay: ${index * 0.1}s`"
          >
            <div class="flex items-center mb-4">
              <div class="w-12 h-12 bg-gradient-to-br from-green-950 to-emerald-950 rounded-lg flex items-center justify-center mr-4">
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
            class="bg-gradient-to-br from-black to-green-950/50 border border-green-800/50 p-9 space-y-6 rounded-2xl shadow-2xl hover-glow animate-slide-up"
            :style="`animation-delay: ${index * 0.15}s`"
          >
            <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between mb-4">
              <h3 class="text-xl sm:text-2xl font-semibold text-green-400 mb-2 sm:mb-0">{{ item.title }}</h3>
            </div>
            <p class="text-gray-300 mb-3">{{ item.organization }}</p>
            <ul class="list-disc list-inside space-y-2 text-gray-400">
              <li v-for="(point, idx) in item.points" :key="idx">{{ point }}</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section id="contacts" class="py-20 px-4 sm:px-6 lg:px-8">
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
            class="bg-gradient-to-br from-black to-green-950/50 border border-green-800/50 p-6 space-y-6 rounded-2xl shadow-2xl hover-glow animate-slide-up"
            :style="`animation-delay: ${index * 0.1}s`"
          >
            <div class="flex flex-col items-center text-center">
              <div class="w-16 h-16 bg-gradient-to-br from-green-950 to-emerald-950 rounded-full flex items-center justify-center mb-4 group-hover:scale-110 transition-transform duration-300">
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
        © {{ new Date().getFullYear() }} Магомедова Амина. Все права защищены.
      </p>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const skills = ref([
  {
    icon: '🔍',
    title: 'База',
    description: 'Основы информационной безопасности, модели угроз, OWASP Top 10'
  },
  {
    icon: '🛡️',
    title: 'Мониторинг безопасности',
    description: 'Понимание принципов работы SIEM (Splunk, Elastic)'
  },
  {
    icon: '📊',
    title: 'ОС',
    description: 'Администрирование Linux, Windows'
  },
  {
    icon: '🔐',
    title: 'Основы сетевой безопасности',
    description: 'базовые знания TCP/IP, модели OSI, VPN, firewall, прокси'
  },
  {
    icon: '💻',
    title: 'Анализ логов',
    description: 'Логи ОС, сетевого оборудования, средств защиты (антивирусов, IDS/IPS)'
  },
  {
    icon: '📚',
    title: 'Скрипты',
    description: 'Bash / Python / PowerShell (чтение чужих скриптов, простые скрипты, автоматизация задач)'
  },
  {
    icon: '📚',
    title: 'Английский язык',
    description: 'Технический, для чтения документации'
  },
  {
    icon: '📚',
    title: 'Личные качества',
    description: 'Обучаемость, стрессоустойчивость, работа в команде'
  }
])

const experience = ref([
    {
      title: 'Опыт',
      organization: 'Практико-ориентированные лаборатории на платформе TryHackMe',
      points: [
        'Анализ инцидентов безопасности',
        'Работа с SIEM-системами',
        'Расследование атак',
        'Анализ сетевого трафика',
        'Триаж инцидентов и классификация событий по уровню критичности',
        'Отработка сценариев реагирования'
      ]
    },
    {
      title: 'Образование',
      organization: 'Дагестанский Государственный Университет',
      points: [
        'Факультет: Информатики и информационных технологий',
        'Направление: Информационная безопасность',
        'Профиль: Безопасность компьютерных систем',
        'Курс: 2'
      ]
    },
])

const contacts = ref([
  {
    icon: '📧',
    title: 'Email',
    value: 'magnus.bat@mail.ru',
    link: 'mailto:magnus.bat@mail.ru'
  },
  {
    icon: '📱',
    title: 'Telegram',
    value: '@mimexx',
    link: 'https://t.me/mimexx'
  },
  {
    icon: '☎️',
    title: 'Телефон',
    value: '+7 (989) 449-29-08',
    link: 'tel:+79894492908'
  }
])
</script>

<style scoped>
html {
  scroll-behavior: smooth;
}
</style>


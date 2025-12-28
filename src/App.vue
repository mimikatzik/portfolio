<template>
  <div class="min-h-screen bg-black text-white">
    <section class="relative py-12 sm:py-16 lg:py-20 px-4 sm:px-6 lg:px-8 overflow-hidden h-screen">
  <div class="absolute inset-0 overflow-hidden">
    <div class="absolute top-20 left-10 w-72 h-72 bg-emerald-500/10 rounded-full blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-20 right-10 w-96 h-96 bg-green-500/10 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 1s;"></div>
  </div>

  <div class="relative z-10 flex items-center min-h-[90vh] xs:h-full">
    <div class="w-full">
      <div class="ml-4 sm:ml-6 lg:ml-8 xl:ml-12">
        <div class="p-6 sm:p-8 lg:p-10">
          <div class="flex flex-col gap-6 sm:gap-8">
              <div class="flex flex-row xs:flex-col gap-6 items-center">
              <div class="flex-shrink-0 animate-slide-in-left">
                <div class="w-32 h-32 xs:w-48 xs:h-48 sm:w-40 sm:h-40 lg:w-48 lg:h-48 rounded-2xl overflow-hidden border-2 border-green-800/50 bg-gradient-to-br from-green-950 to-emerald-950 flex items-center justify-center">
                  <img 
                    v-if="profileData.photo" 
                    :src="profileData.photo" 
                    :alt="profileData.fullName"
                    class="w-full h-full object-cover"
                  />
                  <div v-else class="text-6xl sm:text-7xl lg:text-8xl flex items-center justify-center">
                    <img src="./images/user.png" alt="user" class="w-[60%] object-cover" />
                  </div>
                </div>
              </div>

                <div class="xs:text-center">
                  <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold mb-2">
                    <span class="text-gradient">{{ profileData.fullName }}</span>
                  </h1>
                  <p class="text-xl sm:text-2xl text-green-400 font-semibold mb-1">
                    {{ profileData.position }}
                  </p>
                  <p class="text-gray-400 text-sm sm:text-base">
                    {{ profileData.status }}
                  </p>
                </div>
                </div>

                <div class="grid grid-cols-1 sm:grid-cols-2 sm:max-w-[600px] gap-4 pt-4 border-t border-green-800/30">
                  <div class="flex items-center gap-3">
                    <span class="text-green-400 text-xl flex-shrink-0 flex items-center justify-center">
                      <img src="./images/location.png" class="w-8 h-8 object-cover" />
                    </span>
                    <div>
                      <p class="text-gray-400 text-xs sm:text-sm mb-1">Город</p>
                      <p class="text-gray-200 text-sm sm:text-base">{{ profileData.city }}</p>
                    </div>
                  </div>

                  <div class="flex items-center gap-3">
                    <span class="text-green-400 text-xl flex-shrink-0">
                      <img src="./images/calendar.png" class="w-8 h-8 object-cover" />
                    </span>
                    <div>
                      <p class="text-gray-400 text-xs sm:text-sm mb-1">Дата рождения</p>
                      <p class="text-gray-200 text-sm sm:text-base">{{ profileData.birthDate }}</p>
                    </div>
                  </div>

                  <div class="flex items-center gap-3">
                    <span class="text-green-400 text-xl flex-shrink-0">
                      <img src="./images/briefcase.png" class="w-8 h-8 object-cover" />
                    </span>
                    <div>
                      <p class="text-gray-400 text-xs sm:text-sm mb-1">Желаемая должность</p>
                      <p class="text-gray-200 text-sm sm:text-base">{{ profileData.desiredPosition }}</p>
                    </div>
                  </div>

                  <div class="flex items-center gap-3">
                    <span class="text-green-400 text-xl flex-shrink-0">
                      <img src="./images/online.png" class="w-8 h-8 object-cover" />
                    </span>
                    <div>
                      <p class="text-gray-400 text-xs sm:text-sm mb-1">Формат работы</p>
                      <p class="text-gray-200 text-sm sm:text-base">{{ profileData.workFormat }}</p>
                    </div>
                  </div>

                  <div class="flex items-center gap-3">
                    <span class="text-green-400 text-xl flex-shrink-0">
                      <img src="./images/magnifying-glass.png" class="w-8 h-8 object-cover" />
                    </span>
                    <div>
                      <p class="text-gray-400 text-xs sm:text-sm mb-1">Статус поиска</p>
                      <p class="text-gray-200 text-sm sm:text-base">{{ profileData.jobSearchStatus }}</p>
                    </div>
                  </div>

                  <div class="flex items-center gap-3">
                    <span class="text-green-400 text-xl flex-shrink-0">
                      <img src="./images/university.png" class="w-8 h-8 object-cover" />
                    </span>
                    <div>
                      <p class="text-gray-400 text-xs sm:text-sm mb-1">Образование</p>
                      <p class="text-gray-200 text-sm sm:text-base">{{ profileData.education }}</p>
                    </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        </div>
      </div>
      <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce xs:hidden">
        <svg class="w-6 h-6 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
        </svg>
      </div>
    </section>

    <section id="about" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="container mx-auto max-w-6xl">
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
            <div
              class="w-12 h-12 min-w-12 min-h-12
                     flex-shrink-0
                     bg-gradient-to-br from-green-950 to-emerald-950
                     rounded-lg flex items-center justify-center mr-4"
            >
              <img
                :src="skill.icon"
                alt=""
                class="w-[60%] h-[60%] object-contain opacity-70"
              />
            </div>
            <h3 class="text-xl font-semibold leading-snug">
              {{ skill.title }}
            </h3>
          </div>
            <p class="text-gray-400">{{ skill.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <section id="experience" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="container mx-auto max-w-6xl">
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
      <div class="container mx-auto max-w-6xl">
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
                <span class="text-3xl flex items-center justify-center">
                  <img
                :src="contact.icon"
                alt=""
                class="w-[60%] h-[60%] object-contain opacity-70"
              />
                </span>
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

const profileData = ref({
  fullName: 'Магомедова Амина',
  position: 'SOC L1 Аналитик',
  status: 'Начинающий специалист по кибербезопасности',
  city: 'Махачкала',
  birthDate: '08.05.2007',
  desiredPosition: 'SOC L1 Аналитик',
  workFormat: 'Удаленная работа',
  jobSearchStatus: 'Активно ищу работу',
  education: 'Дагестанский Государственный Университет, 2 курс',
  photo: './images/profile.jpg' 
})

const skills = ref([
  {
    icon: './images/cybersecurity.png',
    title: 'База',
    description: 'Основы информационной безопасности, модели угроз, OWASP Top 10'
  },
  {
    icon: './images/monitoring.png',
    title: 'Мониторинг безопасности',
    description: 'Понимание принципов работы SIEM (Splunk, Elastic)'
  },
  {
    icon: './images/linux.png',
    title: 'ОС',
    description: 'Администрирование Linux, Windows'
  },
  {
    icon: './images/network.png',
    title: 'Основы сетевой безопасности',
    description: 'базовые знания TCP/IP, модели OSI, VPN, firewall, прокси'
  },
  {
    icon: './images/analyze.png',
    title: 'Анализ логов',
    description: 'Логи ОС, сетевого оборудования, средств защиты (антивирусов, IDS/IPS)'
  },
  {
    icon: './images/code.png',
    title: 'Скрипты',
    description: 'Bash / Python / PowerShell (чтение чужих скриптов, простые скрипты, автоматизация задач)'
  },
  {
    icon: './images/english.png',
    title: 'Английский язык',
    description: 'Технический, для чтения документации'
  },
  {
    icon: './images/head-profile.png',
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
    icon: './images/email.png',
    title: 'Email',
    value: 'magnus.bat@mail.ru',
    link: 'mailto:magnus.bat@mail.ru'
  },
  {
    icon: './images/telegram.png',
    title: 'Telegram',
    value: '@mimexx',
    link: 'https://t.me/mimexx'
  },
  {
    icon: './images/phone.png',
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


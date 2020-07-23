<template lang="pug">
  section#works
    Section(title="Примеры работ")
    .content
      Work(v-for="(w, id) in works" :work="w" :isLast="isLastChild(w, works)")
</template>

<script>
import Section from '@/components/Section.vue'
import Work from '@/components/Work.vue'

const username = 'applepieandcrime'
const repo_url = `github.com/${username}/`
const site_url = `${username}.github.io/`
const dynamic_url = '.applepie.darkhost.pro'

export default {
  name: 'WorkExamples',
  components: {
    Section,
    Work
  },
  data() {
    return {
      works: [
        {
          title: 'TO-DO list',
          logo: 'task-card.png',
          description: 'Менеджер задач, привязанный к пользователю.\r\nЕсть авторизация/регистрация.\r\nЗадачи добавляются/изменяются/удаляются через базу данных без перезагрузки страницы.',
          tags: ['PUG','SASS','PHP','JS','MySQL'],
          link_site: 'task-card' + dynamic_url,
          link_repo: repo_url + 'task-card-php'
        },
        {
          title: 'Boots',
          logo: 'boots.png',
          description: 'Статичный лендинг с адаптивной версткой.',
          tags: ['PUG','SASS','JS','GULP'],
          link_site: site_url + 'boots/dist',
          link_repo: repo_url + 'boots'
        },
        {
          title: 'Текстовая РПГ',
          logo: '',
          description: 'Сделан в Visual Studio Code.\r\nКаждая новая игра случайно распределяет колдунов/предметы на поле. Нужно отдать конкретный предмет колдуну, ориентируюсь на его подсказки. Предметы можно подбирать и выкладывать (хранилище вмещает не больше 4 предметов).\r\nСохранение происходит с помощью создания/редактирования json файлов в папке с относительным путем (можно удалить папку: программа пересоздаст её).\r\nДоступно управление клавиатурой/мышью.',
          tags: ['C#','JSON'],
          link_site: false,
          link_repo: repo_url + 'text-rpg'
        },
        {
          title: 'UFO',
          logo: false,
          description: 'Сделан на констукторе "Construct 2".\r\nИгра-бродилка, в которой главный герой-инопланетянин должен выбраться из комнат.\r\nСохранение/загрузка работает с кешем.\r\nВозможность выбора сенсорного управления.',
          tags: [],
          link_site: site_url + 'UFO',
          link_repo: repo_url + 'ufo'
        },
        // {
        //   title: '',
        //   logo: '',
        //   description: '',
        //   tags: ['',''],
        //   link_site: site_url + '',
        //   link_repo: repo_url + ''
        // },
      ]
    }
  },
  methods: {
    isLastChild: function (item, array) {
      return item == array[array.length - 1]
    }
  }
}
</script>

<style lang="sass" scoped>
.section
  margin-bottom: 30px
</style>

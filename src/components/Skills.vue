<template lang="pug">
  section#skills
    Section(title="Навыки")
    .content
      p.skills-item(v-for="skill in skills") {{skill}}
</template>

<script>
import Section from '@/components/Section.vue'

export default {
  name: 'Skills',
  components: {
    Section
  },
  data() {
    return {
      skills: [
        'HTML & CSS & JS (препроцессоры: PUG, SASS)',
        'работа с SQL (MS SQL, MySQL)',
        'общие навыки работы с GIT',
        'работа с gulp',
        'разработка на Vue',
        'примитивная работа с сервером: размещение файлов и настройка поддоменов'
      ]
    }
  }
}
</script>

<style lang="sass" scoped>

.content
  width: 80%
  padding: 0 0 0 10%

$line-height: 1.2em
$before-pad: -($line-height + 0.6em)

.skills
  &-item
    position: relative
    font-size: $line-height
    line-height: $line-height + 0.1em
    padding: 5px 0
    &::before
      position: absolute
      content: ''
      background-image: url("~@/assets/sweet.svg")
      background-repeat: no-repeat
      background-size: cover
      width: $line-height + 0.1em
      height: $line-height + 0.1em
      top: 50%
      left: $before-pad
      transform: translateY(-50%) 
      
@media screen and (max-width: 680px)
  $line-height: 1.1em

</style>

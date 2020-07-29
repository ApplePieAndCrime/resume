<template lang="pug">
  section#about
    Section(title="Обо мне")
    .content
      .photo
        img(src="~@/assets/my-photo.jpg")
      .text-content
        h3 Ирина, 21
        p {{about}}
</template>

<script>
import Section from '@/components/Section.vue'

export default {
  name: 'About',
  components: {
    Section
  },
  data() {
    return {
      about: "Верстаю на препроцессорах html(pug) и css(sass) с gulp'ом."
        + '\r\nЕсть опыт разработки баз данных на MS SQL и MySQL.'
        + '\r\nЕсть базовые навыки работы с git.'
        + '\r\nДля удобства делаю макеты в Figma или для PSD использую Avocode.'
    }
  }
}
</script>

<style lang="sass" scoped>

.content
  display: flex

$photo-size: 200px
.photo
  min-width: 30%
  margin-right: 20px
  img
    width: 150px
    height: 150px
    border-radius: 50%
    background-size: contain

h3
  margin: 10px 0
  text-align: left
  font-size: 1.7em
  color: #AAAA8E
  font-weight: 500

p
  font-size: 1em

.text-content

  white-space: pre-wrap

@media screen and (max-width: 480px)
  .photo
    width: 100%

</style>

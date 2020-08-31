<template lang="pug">
  section#about
    Section(title="Обо мне")
    .content
      .photo
        img.photo-img(src="~@/assets/my-photo.jpg")
      .text-content
        h3 Ирина, {{year}}
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
      year: Math.floor((new Date() - new Date(1999,5,8)) / 31536000000),
      about: "Верстаю на препроцессорах html (pug) и css (sass) с gulp'ом или VueJS."
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
  justify-content: space-around

$photo-size: 200px
.photo
  max-width: 28%
  margin-right: 20px
  display: flex
  align-items: center

  &-img
    width: 100%
    border-radius: 50%

.text-content
  display: flex
  flex-direction: column
  padding-top: 15px

h3
  margin: 10px 0
  text-align: left
  font-size: 1.7em
  color: #AAAA8E
  font-weight: 500

p
  white-space: pre-wrap
  line-height: 1.5em

@media screen and (max-width: 1200px)
  .text-content
    padding-top: 0
  .photo
    min-width: 35%

@media screen and (max-width: 900px)
  .text-content
    padding-top: 0
    h3
      text-align: center
    p
      font-size: 1em
  .content
    flex-direction: column
  .photo
    min-width: 50%
    margin: auto

</style>

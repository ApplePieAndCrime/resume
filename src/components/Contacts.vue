<template lang="pug">
  section#contacts
    Section(title="Контакты")
    .content
      p Мой github-аккаунт: 
        a(:href="'//' + github") {{github}}
</template>

<script>
import Section from '@/components/Section.vue'

export default {
  name: 'Contacts',
  components: {
    Section
  },
  data() {
    return {
      github: 'github.com/ApplePieAndCrime'
    }
  }
}
</script>

<style lang="sass" scoped>

.content
  width: 80%
  margin-top: 30px
  p
    margin: 10px 0

a
  text-decoration: none
  color: #B2B2AF
  &:hover
    cursor: pointer
    text-decoration: underline

</style>

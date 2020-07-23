<template lang="pug">
  #app
    Nav
    About
    Skills
    WorkExamples
    Contacts
</template>

<script>
import Nav from '@/components/Nav.vue'
import Section from '@/components/Section.vue'
import About from '@/components/About.vue'
import Skills from '@/components/Skills.vue'
import WorkExamples from '@/components/WorkExamples.vue'
import Contacts from '@/components/Contacts.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Section,
    About,
    Skills,
    WorkExamples,
    Contacts
  }
}
</script>

<style lang="sass">

body
  margin: 0
  padding-top: 70px
  background-color: #E5E5E5
  font-family: Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  color: #24292E
  font-family: 'Raleway'
  position: relative
  
#app
  scroll-behavior: smooth

</style>

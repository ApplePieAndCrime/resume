<template lang="pug">
  .nav
    ul.menu
      li.menu-item(v-for="item in menu") 
        a(:href="item.link" @click="scrollToSection") {{ item.name }}

</template>

<script>
export default {
  name: 'Nav',
  data: function() {
    return {
      menu: [
        { name:'Обо мне', link:'#about' },
        { name:'Навыки', link:'#skills' },
        { name:'Примеры работ', link:'#works' },
        { name:'Контакты', link:'#contacts' }
      ]
    }
  },
  methods: {
    scrollToSection: (e) => {
      const sectionUrl = e.target.href.substring(e.target.href.indexOf('#'))
      const section = document.querySelector(sectionUrl)
      const headerOffset = 59 + 20
      const sectionPos = section.getBoundingClientRect().top

      e.preventDefault()

      window.scrollTo({
        top: sectionPos + pageYOffset - headerOffset,
        behavior: "smooth"
      })
    }
  }
}

</script>

<style lang="sass" scoped>

.nav
  background-color: #24292E
  position: fixed
  top: 0
  width: 100%
  z-index: 1

.menu
  list-style: none
  margin: auto
  padding: 20px 0
  width: 70%
  
  display: flex
  justify-content: space-around

  &-item
    
a
  text-decoration: none
  color: #F1F4F7
  font-weight: bold
  &:hover
    color: #e6eaed
  &:active
    color: #c5c8c9
  
@media screen and (max-width: 480px)
  .menu
    flex-direction: column
    align-items: center
    &-item
      margin: 5px 0

</style>

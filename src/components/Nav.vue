<template lang="pug">
  nav
    .menu-icon
      input(id="toggle-menu" type="checkbox" @change="toggleMenu")
      span
      span
      span
    .nav
      ul.menu
        li.menu-item(v-for="item in menu") 
          a(:href="item.link" @click.prevent="scrollToSection") {{ item.name }}

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
      let headerOffset = 59 + 20
      const sectionPos = section.getBoundingClientRect().top

      if(window.innerWidth <= 560) {
        const input = document.querySelector('#toggle-menu')
        input.checked = false
        headerOffset = 22
        
        const event = new CustomEvent('change')
        input.dispatchEvent(event)
      }

      window.scrollTo({
        top: sectionPos + pageYOffset - headerOffset,
        behavior: "smooth"
      })

    },
    toggleMenu: (e) => {
        const nav = document.querySelector('.nav')
        const input = e.target

        nav.classList.toggle('nav-show')
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

.menu-icon
  display: none

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
  
@media screen and (max-width: 560px)
  .nav
    transform: translate(0, -100%)
    transition: transform 0.5s ease
  .nav-show
    transform: none
    
  .menu-icon
    position: fixed
    top: 15px
    left: 15px
    display: block
    user-select: none
    z-index: 3
    input
      display: block
      position: absolute
      top: -7px
      left: -5px
      width: 40px
      height: 32px
      cursor: pointer
      opacity: 0
      z-index: 99
      -webkit-touch-callout: none

      &:checked 
        & ~ span
          margin: 0
          background-color: #fff
          &:nth-child(2)
            transform: rotate(45deg) translate(0px, 0px)
          &:nth-child(3)
            opacity: 0
            transform: rotate(0deg) scale(0.2, 0.2)
          &:nth-child(4)
            transform: rotate(-45deg) translate(-10px, 10px)

    span
      display: block
      width: 33px
      height: 4px
      margin-bottom: 5px
      background-color: #24292E
      position: relative
      border-radius: 3px
      z-index: 1
      transform-origin: 4px 0px
      transition: transform .5s cubic-bezier(0.77,0.2,0.05,1.0), background .5s cubic-bezier(0.77,0.2,0.05,1.0), opacity .55s ease, margin .5s cubic-bezier(0.77,0.2,0.05,1.0)
      &:nth-child(2)
        transform-origin: 0% 0%
      &:nth-child(4)
        transform-origin: 0% 100%

  .menu
    flex-direction: column
    align-items: center
    &-item
      margin: 5px 0

</style>

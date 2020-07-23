<template lang="pug">
  section#about
    Section(title="Обо мне")
    .content
      .photo
        img(src="~@/assets/photo.jpeg")
      .text-content
        h3 Ирина, 21
        p Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolores, quia. Mollitia tenetur neque ab nisi perspiciatis, placeat saepe. Incidunt beatae nisi maiores ratione voluptatum distinctio ipsam expedita cupiditate animi, est rerum ipsum. Iste pariatur necessitatibus fugit facilis nam. Repellendus, quia error. Magni harum fugit, quae iste veritatis accusamus porro officia, molestiae nulla ipsum voluptate aliquam incidunt totam eaque illum odit?
</template>

<script>
import Section from '@/components/Section.vue'

export default {
  name: 'About',
  components: {
    Section
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
    width: 100%
    height: auto
    border-radius: 50%

h3
  margin: 10px 0
  text-align: left
  font-size: 1.7em
  color: #AAAA8E
  font-weight: 500

@media screen and (max-width: 480px)
  .photo
    width: 100%

</style>

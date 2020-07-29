<template lang="pug">
  .section
    h2.heading-title {{title}}
    .heading-line

</template>

<script>
export default {
  name: 'Section',
  props: {
    title: String
  }
  
}
</script>

<style lang="sass">

section
  background-color: #FFFFFF
  margin: 35px 15%
  padding: 20px 30px 40px
  text-align: center

p
  margin: 0
  padding: 0
  font-size: 1.1em

.section
  width: 80%
  margin: auto

.content
  width: 90%
  margin: auto
  margin-top: 20px
  text-align: left

.heading
  &-title
    font-size: 34px
    margin: 0 0 2px
  &-line
    background-color: #E1E4E8
    height: 2px

@media screen and (max-width: 768px)
  section
    margin: 35px 10%

@media screen and (max-width: 480px)
  section
    margin: 25px 15px
    padding: 30px 20px

</style>

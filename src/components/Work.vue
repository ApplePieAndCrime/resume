<template lang="pug">
  .work
    .work-header
      img.logo-img(v-if="work.logo" :src="require(`@/assets/${work.logo}`)" alt="лого")
      img.logo-img(v-else src="@/assets/no-logo.png" alt="лого")
      h3.work-title {{work.title}}
    p.work-description {{work.description}}
    Tag(:tags="work.tags")
    .link-wrapper
      .link(v-if="work.link_site") 
        mark.special-site Ссылка на сайт:
        a(:href="'//' + work.link_site") {{work.link_site}}
      .link(v-if="work.link_repo")  
        mark.special-repo Ссылка на репозиторий:
        a(:href="'//' + work.link_repo") {{work.link_repo}}
    .break-line(v-if="!isLast")
</template>

<script>
import Tag from "@/components/Tag.vue"

export default {
  name: 'Work',
  components: {
    Tag
  },
  props: {
    work: Object,
    isLast: {
      type: Boolean,
      default: false
    }
  },
  // {
  //   title: String,
  //   logo: String,
  //   description: String,
  //   tags: Array,
  //   link_site: String,
  //   link_repo: String
  // }
}
</script>

<style lang="sass" scoped>

.work
  &-header
    display: flex
    align-items: center
    margin: 0 0 20px
  &-title
    margin: 0
  &-description
    margin: 0 0 30px
    white-space: pre-wrap
    line-height: 1.5em

.logo-img
  width: 40px
  height: 40px
  margin-right: 10px

mark
  background-color: transparent
  font-weight: 600
  margin-right: 6px

.link
  &-wrapper
    margin: 15px 0
  a
    text-decoration: none
    color: #B2B2AF
    &:hover
      cursor: pointer
      text-decoration: underline

.special
  &-site
    color: #2A76E9
  &-repo
    color: #CB2A34

.break-line
  background-color: #E1E4E8
  height: 2px
  width: 30%
  margin: 40px auto

@media screen and (max-width: 768px)
  .link
    display: flex
    flex-direction: column

</style>

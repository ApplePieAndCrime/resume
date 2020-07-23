<template lang="pug">
  .tag-list
    .tag(v-for="tag in tags") {{tag}}
</template>

<script>
export default {
  name: 'Tag',
  props: {
    tags: Array
  }
}
</script>

<style lang="sass" scoped>
.tag
  background-color: #D6F5D9
  color: #6AA771
  padding: 5px 10px
  margin-right: 10px
  border-radius: 5px
  &-list
    display: flex
</style>
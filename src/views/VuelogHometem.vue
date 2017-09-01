<template>
  <div class="MyComponent">
    <vue-typer text='Hello World! I was registered locally!'></vue-typer>
  </div>
</template>

<script>
  import { VueTyper } from 'vue-typer'

  export default {
    // ...
    components: {
      // <my-component> will only be available in parent's template
      'vue-typer': VueTyper
    }
  }
</script>

<style lang="stylus" scoped>
  .home
    text-align center

  img
    display inline-block
    height 256px
    width 256px
    margin-top 75px

  h1
    font-weight 300
    font-size 60px
    margin-top 16px
    margin-bottom 36px

  p
    color #7f8c8d
    font-size 20px
    margin-bottom 24px

  .github
    background #fff
    color #4fc08d

    &:hover
      background #fcfcfc
      color #5dc596

  @media screen and (max-width: 999px)
    img
      height 192px
      width 192px
      margin-top 32px

    h1
    p
      margin-top 15px
      margin-bottom 15px

    .button
      margin-bottom .25em
</style>

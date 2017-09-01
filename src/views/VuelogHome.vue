<template>
  <div class="home">
    <br>
    <div class="com">
      <div class="words">
        <vue-typer :text='["Hi, Welcome to Feiou`s personal website!","Please help yourself play around here.","And I would love to share something with you in this website, maybe ideas, maybe tips, how I solved a problem, or just some random thoughts.","I believe in what Benjamin Franklin says `Any investment in knowledge always pays the best interest.` I hope we all can learn something along the way."]'
                   :repeat = '0'
                   :typeDelay = '100'
        ></vue-typer>
      </div>
    </div>
  </div>
</template>

<script>
  import { retrieveByLanguage } from '../helpers'
  import { VueTyper } from 'vue-typer'

  export default {
    name: 'vuelog-home',
    components: {
      'vue-typer': VueTyper
    },
    computed: {
      active () {
        return this.$store.getters.lang
      },

      config () {
        return this.$store.getters.config
      },

      system () {
        return this.$store.getters.system
      },

      download () {
        return `${this.system.project}/releases/latest`
      },

      title () {
        return retrieveByLanguage(this.config.brand, this.active, this.config.defaultLang)
      }
    },

    created () {
      this.$store.dispatch('documentTitle', this.title)
    },

    watch: {
      $route (to, from) {
        if (to.query.lang !== from.query.lang) {
          this.$store.dispatch('documentTitle', this.title)
        }
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .vue-typer
    font-family monospace
    font-size x-large
    text-align left

  .com
    position: absolute
    background-image: url(../assets/img/imac.png)
    background-size cover
    height 646px
    width 800px

  .words
    position absolute
    margin-left 10%
    margin-top 10%
    margin-right 10%
  .home
    text-align center

  img
    display inline-block
    height 646px
    width 800px
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
    .com
      position: absolute
      background-image: url(../assets/img/ipad63.png)
      background-size cover
      height 870px
      width 620px
      margin-top 5%
      margin-left 5%
    .vue-typer
      font-size xx-large

    .words
      position absolute
      margin-left 13%
      margin-top 23%
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
  @media screen and (max-width: 707px)
    .com
      position: absolute
      background-image: url(../assets/img/62.png)
      background-size cover
      height 630px
      width 310px
    .vue-typer
      font-size large

    .words
      position absolute
      margin-left 10%
      margin-top 35%
</style>

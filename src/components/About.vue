<template>
  <section id="about">
    <div class="row">
      <div class="columns">
        <h4>{{ conf.menu.about }}</h4>
        <div class="about-wrapper">
          <div class="row" v-bind:class="$index == 0 ? 'single' : ''" v-for="abouts in conf.abouts">
            <avatar v-for="detail in abouts" :detail="detail" :type="type"></avatar>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    data: () ->
      return {
        type: 'about'
      }
    components:
      avatar: require './Avatar.vue'
    props: ['conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'

  #about
    h4
      text-align: center
      margin-top: 4rem
      margin-bottom: 2rem
    .about-wrapper
      text-align: center
      /*padding: 0 1rem*/
      /*+breakpoint(small only)*/
        /*width: 100%*/
        /*padding: 0*/
        /*margin: 0*/
</style>

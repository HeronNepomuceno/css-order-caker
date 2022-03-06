<template>
  <header-comp></header-comp>
  <action-comp></action-comp>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import ActionComp from './components/ActionComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    ActionComp
  }
}
</script>

<style lang="stylus">
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500&display=swap')

:root
  --fontPrimary 'Quicksand', sans-serif
  --fontColor #31111D
  --bgColorPrimary #31111D
  --bgColorSecondary #FFD8E4
  --bgColorTertiary #FFECF1

*
  margin 0
  padding 0
  border 0

body
  background var(--bgColorPrimary)
  width 100%
  height 100%

textarea
    overflow auto
    outline none
    -webkit-box-shadow none
    -moz-box-shadow none
    box-shadow none
    resize none
    border solid 1px var(--fontColor)
		border-radius 15px
		background var(--bgColorTertiary)

h3
	margin 0
	padding 0
	border 0
	outline 0
	font-weight inherit
	font-style inherit
	font-size 100%
	font-family inherit
	vertical-align baseline

button
  cursor pointer

</style>

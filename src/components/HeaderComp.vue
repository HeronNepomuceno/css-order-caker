<template>
	<header>
		<div class="title-wrapper">
			<svg>
				<use xlink:href="../assets/sprite.svg#candle"></use>
			</svg>
			<h1 class="title">CSS ORDER CAKER</h1>
			<span class="info">Tool developed to organize your CSS in alphabetical order.</span>
		</div>
		<div class="usability-wrapper">
			<div class="usability-head">
				<h6>{{ how_to_use1 }}</h6>
			</div>
			<div class="usability-body">
				<textarea value=".class {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}" disabled></textarea>
				<svg>
					<use xlink:href="../assets/sprite.svg#right-arrow"></use>
				</svg>
				<textarea value=".class {
  align-items: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
}" disabled></textarea>
			</div>
			<div class="usability-footer">
				<h6>{{ how_to_use2 }}</h6>
			</div>
		</div>
	</header>
</template>

<script>
export default {
	name: 'HeaderComp',
	data: function () {
    return {
      how_to_use1: 'Write your css in the input:',
      how_to_use2: 'It will come back in alphabetical order!'
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
header
	display flex
	justify-content space-between
	margin-top 16px
	width 100%

	.title-wrapper
		background var(--bgColorSecondary)
		border-radius 5px
		padding 16px 32px
		border solid 2px #000
		display flex
		justify-content center
		align-items center
		flex-direction column
		margin-left 32px

	svg
		height 64px
		width 64px
		fill #31111D

	.title
		font-family var(--fontPrimary)
		font-weight 500
		text-align center
		margin-top 12px
		font-size 32px
		color var(--fontColor)

	.info
		font-family var(--fontPrimary)
		font-weight 400
		text-align center
		margin-top 6px
		font-size 18px
		color var(--fontColor)

.usability-wrapper
	background var(--bgColorSecondary)
	border-radius 5px
	padding 16px 32px
	border solid 2px #000
	margin-right 32px

	h6
		font-family var(--fontPrimary)
		font-weight 500
		font-size 20px
		color var(--fontColor)

	textarea
		width 240px
		height 100px

	.usability-head
		width 100%
		margin-bottom 32px
		display flex
		justify-content flex-start

	.usability-body
		width 100%
		display flex
		justify-content space-between
		align-items center

		svg
			width 16px
			height 16px
			margin 0 16px

	.usability-footer
		width 100%
		margin-top 32px
		display flex
		justify-content flex-end

</style>

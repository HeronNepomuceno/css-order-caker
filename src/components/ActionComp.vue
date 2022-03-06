<template>
	<main class="action-wrapper">
		<div class="action">
			<section class="select">
				<div class="options-wrapper">
					<label class="label">Choose your css tecnology:</label>
					<select class="options" name="select">
						<option value="choice-css">Pure Css</option>
					</select>
				</div>
				<div class="options-wrapper">
					<label class="label">Choose order type:</label>
					<select class="options" name="select">
						<option value="choice-css">Alphabetical</option>
					</select>
				</div>
			</section>
			<section class="order">
				<div class="order-head">
					<h3>Write your css in the textarea and click in the button:</h3>
				</div>
				<div class="order-body">
					<textarea class="input"></textarea>
					<svg>
						<use xlink:href="../assets/sprite.svg#right-arrow"></use>
					</svg>
					<textarea class="output" v-model="output_css" disabled> </textarea>
				</div>
				<div class="order-footer">
					<button class="order" @click="getInputCss">Order</button>
				</div>
			</section>
		</div>
	</main>
</template>

<script>
export default {
	name: 'ActionComp',
	data () {
		return {
			input_css: '',
			output_css: ''
		}
	},
	methods: {
		getInputCss() {
			// Pegando o antigo css no input.
			let input_value = document.querySelector('.input').value

			// Formatando o antigo css para um formato manipulável.
			let old_css_covert = input_value.replace(/\n/g, '').split('}')
			for (let i = 0; i <= old_css_covert.length-1; i++) {
				old_css_covert[i] = old_css_covert[i] + '  }'
			}
			old_css_covert.length = old_css_covert.length-1
			this.input_css = old_css_covert

			// Chamando a função de transformação
			this.transformCss(this.input_css)
		},

		transformCss(old_css_covert) {
			let inside_old_css_covert = []
			let inside_new_css_covert = []
			let class_name_css = []

			// Percorrendo o array do antigo css e separando somente o conteúdo entre as { }.
			for (let i = 0; i <= old_css_covert.length-1; i++) {
				let inside = old_css_covert[i].substring(
					old_css_covert[i].indexOf("{") + 1, 
					old_css_covert[i].lastIndexOf("}")
				)
				inside_old_css_covert.push(inside)
			}

			// Percorrendo a parte de dentro do array, e ordenando os items em ordem alfabética.
			for (let i = 0; i <= inside_old_css_covert.length-1; i++) {
				let split_inside_array = inside_old_css_covert[i].split(';')
				inside_new_css_covert.push(split_inside_array.sort() + ';')
			}

			// Pegando o nome de todas as classes
			for (let i = 0; i <= old_css_covert.length-1; i++) {
				let inside = old_css_covert[i].substring(
					old_css_covert[i].indexOf('#') + 1, 
					old_css_covert[i].lastIndexOf("{")
				)
				class_name_css.push(inside)
			}

			// Chamando a função geradora do novo css ordenado
			this.gerateOrderCss(class_name_css, inside_new_css_covert)
		},

		gerateOrderCss(class_name, css_order_inside) {
			let order_css = []

			// Juntando o array de classes com o array de items ordernados em ordem alfabética
			for (let i = 0; i <= class_name.length-1; i++) {
				let inside = `.${class_name[i]} {\n${css_order_inside[i]}}`
				order_css.push(inside)
			}
			
			// Formatação da string para uma melhor visualização no input
			for (let i = 0; i <= order_css.length-1; i++){
				order_css[i] = order_css[i].replace(/,/g, ';')
				order_css[i] = order_css[i].replace(';', ' ')
				order_css[i] = order_css[i].replace(/;/g, ';\n')
				order_css[i] = order_css[i].replace(/ /g, '')
				order_css[i] = order_css[i].replace(/{/g, ' {')
				order_css[i] = order_css[i].replace(/,/g, ' \n')
			}
			this.output_css = order_css.toString()
			this.output_css = this.output_css.replace(/,/g, '\n')
		}
	}
}
</script>

<style scoped lang="stylus">
.action-wrapper
	display flex
	justify-content space-between
	padding 32px

.action
	width 100%
	display flex
	background var(--bgColorSecondary)
	border solid 2px #000
	padding 16px 32px
	border-radius 5px
	justify-content space-between

.select
	display flex
	flex-direction column
	align-items center
	justify-content center
	border-right 1px solid #000
	padding-right 48px
	border-radius 5px

.options-wrapper
	display flex
	flex-direction column
	width 100%
	margin 16px 0

.label
	font-family var(--fontPrimary)
	color var(--fontColor)
	font-size 22px
	margin-bottom 8px

.options
	background var(--bgColorTertiary)
	border solid 1px var(--fontColor)
	border-radius 5px

.order
	display flex
	flex-direction column
	align-items center
	margin-left 5vw

.order-head
	display flex
	justify-content space-between
	width 100%
	margin-top 16px
	align-items center

	h3
		font-family var(--fontPrimary)
		color var(--fontColor)
		font-size 22px
		margin-right 48px

.order-body
	display flex
	justify-content space-between
	align-items center
	width 100%
	margin-top 32px

	.input
		width 400px
		height 280px
		font-size 14px

	svg
		height 32px
		width 32px
		fill #31111D
		margin 0 8px

	.output
		width 400px
		height 280px
		font-size 14px

.order-footer
	display flex
	margin-top 32px
	width 100%
	align-items center
	justify-content flex-end

	.order
		padding 8px 32px
		background var(--fontColor)
		border-radius 15px
		color var(--bgColorTertiary)
		font-size 16px
		opacity 1
		transition opacity, transform, .5s, .5s

		&:hover
			opacity .8

		&:active
			transform scale(.9)
</style>

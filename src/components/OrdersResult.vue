<template>
	<div class="orders-result">
		<p class="orders-result__text">
			<span class="value">2.345</span> pedidos encontrados <span class="line hide-for-mobile">|</span> <br class="break show-for-mobile" />no <span class="hide-for-mobile">valor</span> total de <span class="value">R$35.056,00</span>
		</p>
		<a href="#" class="orders-result__link orders-result--export">Exportar Planilha</a>
		<a href="#" class="orders-result__link orders-result--hide show-for-mobile">Esconder Cliente</a>
	</div>
</template>

<script>
	export default {
		name: 'orders-result'
	}
</script>

<style scoped>
	.orders-result {
		border-bottom: 1px solid #FFF;
		padding: 25px 0;
		position: relative;
		width: 100%;
	}

		.orders-result__text {
			color: #1C448C;
			display: inline-block;
			font-size: 12px;
			font-weight: 700;
			letter-spacing: 2px;
			line-height: 13px;
			text-transform: uppercase;
		}

		.orders-result__text .break {
			display: none;
		}

		.orders-result__text .value {
			display: inline-block;
			font-size: 18px;
			font-weight: 400;
			letter-spacing: 1px;
			vertical-align: top;
		}

		.orders-result__text .line {
			display: inline;
			padding: 0 8px;
		}

		.orders-result__link {
			color: #1C448C;
			float: right;
			display: block;
			font-size: 14px;
			font-weight: 700;
			letter-spacing: .4px;
			padding-left: 28px;
			text-decoration: none;
			text-transform: uppercase;
		}

	.orders-result--export {
		background: url("./../assets/icon-export.svg") no-repeat left center;
	}

	.orders-result--hide {
		background: url("./../assets/icon-hide.svg") no-repeat left center;
	}

	@media all and (max-width: 800px) {
		.orders-result {
			border-bottom: none;
			padding: 35px 0;
		}

			.orders-result__text,
			.orders-result__link {
				display: block;
				line-height: 28px;
				margin: 0 auto;
				text-align: center;
			}
			
			.orders-result__text {
				margin-bottom: 24px;
			}

			.orders-result__link {
				float: none;
				max-width: 182px;
				justify-content: center;
			}

		.orders-result--export {
			margin-bottom: 20px;
		}

		.orders-result--hide {
			display: block;
		}
	}
</style>
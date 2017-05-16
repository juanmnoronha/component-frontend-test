<template>
	<div class="orders-head hide-for-mobile">
		<div class="orders-head__row">
			<div class="orders-head__col orders-head--first">
				<div class="orders-head__col orders-head--status">
					<a class="orders-head__link" href="#">Status</a>
				</div>
				<div class="orders-head__col orders-head--code">
					<a class="orders-head__link" href="#">Código</a>
				</div>
			</div>
			<div class="orders-head__col orders-head--second">
				<div class="orders-head__col orders-head--payment-method">
					<a class="orders-head__link" href="#">Meio</a>
				</div>
				<div class="orders-head__col orders-head--amount">
					<a class="orders-head__link" href="#">R$</a>
				</div>
				<div class="orders-head__col orders-head--updated">
					<a class="orders-head__link" href="#">Atualizado</a>
				</div>
			</div>
			<div class="orders-head__col orders-head--third">
				<div class="orders-head__col orders-head--customer">
					<a class="orders-head__link" href="#">Cliente</a>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'orders-head'
	}
</script>

<style>
	.orders-head {
		margin-bottom: 10px;
		overflow: hidden;
		position: relative;
		width: 100%;
	}

		.orders-head__link {
			color: #FFF;
			font-size: 16px;
			font-weight: 700;
			line-height: 18px;
			text-decoration: none;
		}

		.orders-head__row {
			align-items: center;
			display: flex;
			flex-flow: row nowrap;
		}

		.orders-head__col {
			display: flex;
			flex-flow: row nowrap;
			position: relative;
			word-break: break-word;
		}

		.orders-head__col.order-by {
			color: #1C448C;
		}

	.order-by__btn {
		background: url("./../assets/icon-order-by.svg") center center;
		display: inline-block;
		height: 10px;
		margin: 5px;
		vertical-align: middle;
		width: 10px;
	}

	.orders-head--first,
	.orders-head--second,
	.orders-head--third {
		align-items: center;
	}

	.orders-head--first {
		width: 32%;
	}

	.orders-head--second {
		width: 36%;
	}

	.orders-head--third {
		width: 32%;
	}

	.orders-head--status {
		justify-content: center;
		width: 26%;
	}

	.orders-head--code {
		padding-left: 2%;
		width: 72%;
	}

	.orders-head--payment-method {
		justify-content: center;
		width: 18%;
	}

	.orders-head--amount {
		width: 36%;
	}

	.orders-head--updated {
		width: 46%;
	}

	.orders-head--customer {
		width: 100%;
	}

	.orders-head--customer .orders-head__link {
		padding-left: 16px;
	}
</style>
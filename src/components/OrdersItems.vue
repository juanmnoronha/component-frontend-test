<template>
	<div class="orders-items">
		<div class="orders-items__row orders-items__item" v-for="order in orders">
			<div class="orders-items__col orders-items--first">
				<div class="orders-items__col orders-items--status" :class="'is-' + order.status">
					<i class="icon"></i>
				</div>
				<div class="orders-items__col orders-items--code mask">{{ order.code }}</div>
			</div>
			<div class="orders-items__col orders-items--second">
				<div class="orders-items__col orders-items--payment-method is-ticket" :class="'is-' + order.paymentMethod">
					<i class="icon"></i>
				</div>
				<div class="orders-items__col orders-items--amount mask">{{ order.amount }}<span class="bullet show-for-mobile">•</span></div>
				<div class="orders-items__col orders-items--updated mask" v-for="updated in order.updated">{{ updated.date }} • {{ updated.hour }}</div>
			</div>
			<div class="orders-items__col orders-items--third">
				<div class="orders-items__col orders-items--customer mask">
					<div class="customer border" v-for="customer in order.customer">
						<div class="customer__type">{{ customer.type }}</div>
						<div class="customer__fullname">{{ customer.fullname }}</div>
						<div class="customer__email">{{ customer.email }}</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'orders-items',

		data() {
			return {
				orders: [
					{
						status: 'paid',
						code: 'ABC23457983211XB234',
						paymentMethod: 'ticket',
						amount: '239,00',
						updated: [
							{
								date: '01/11/16',
								hour: '18h16'
							}
						],
						customer: [
							{
								type: 'NC',
								fullname: 'Maude Glover',
								email: 'hirthe.tyreek@esta.org'
							}
						]								
					},
					{
						status: 'not-paid',
						code: 'ABC23457983211XB234',
						paymentMethod: 'ticket',
						amount: '457,34',
						updated: [
							{
								date: '05/12/16',
								hour: '19h20'
							}
						],
						customer: [
							{
								type: 'NC',
								fullname: 'Patrick Hodges',
								email: 'sabrina.lowe@yahoo.co'
							}
						]								
					},
					{
						status: 'paid',
						code: 'ABC23457983211XB234',
						paymentMethod: 'credit-card',
						amount: '999.739,99',
						updated: [
							{
								date: '06/11/16',
								hour: '19h35'
							}
						],
						customer: [
							{
								type: 'NC',
								fullname: 'Dustin Underwood',
								email: 'alisha_nitzsche@bashiri'
							}
						]								
					},
					{
						status: 'paid',
						code: 'ABC23457983211XB234',
						paymentMethod: 'debit-card',
						amount: '999.739,99',
						updated: [
							{
								date: '06/11/16',
								hour: '19h35'
							}
						],
						customer: [
							{
								type: 'NC',
								fullname: 'Melvin Patterson',
								email: 'pfeffer_lisette@delta.co'
							}
						]								
					},
					{
						status: 'paid',
						code: 'ABC23457983211XB234',
						paymentMethod: 'debit-card',
						amount: '99.739,99',
						updated: [
							{
								date: '06/11/16',
								hour: '19h35'
							}
						],
						customer: [
							{
								type: 'NC',
								fullname: 'Inez Knight',
								email: 'langosh_adonis@yahoo.'
							}
						]								
					}
				]
			}
		}
	}
</script>

<style scoped>
	.orders-items {
		display: flex;
		flex-flow: column nowrap;
		position: relative;
		justify-content: space-between;
		width: 100%;
	}

	.orders-items .icon {
		display: block;
		background-position: center center;
		background-repeat: no-repeat;
		height: 24px;
		width: 24px;
	}

		.orders-items__item {
			background: #FFF;
			border-radius: 100px;
			clear: both;
			color: #1C448C;
			font-size: 14px;
			font-weight: 400;
			height: 58px;
			letter-spacing: 1px;
			line-height: 15px;
			margin-bottom: 9px; 
			overflow: hidden;
			padding: 12px 0;
		}

		.orders-items__item:hover {
			box-shadow: 0 8px 8px 0 rgba(28,68,140,0.41), 0 2px 2px 0 rgba(28,68,140,0.50), 0 4px 4px 0 rgba(28,68,140,0.40);
		}

		.orders-items__row {
			align-items: center;
			display: flex;
			flex-flow: row nowrap;
		}

		.orders-items__col {
			display: flex;
			flex-flow: row nowrap;
			position: relative;
			word-break: break-word;
		}

		.orders-items__col.mask {
			position: relative;
		}

		.orders-items__col.mask:after {
			background-image: linear-gradient(90deg, rgba(255,255,255,0.00) 3%, #FFF 99%);
			content: "";
			display: block;
			height: 100%;
			position: absolute;
			right: 0;
			top: 0;
			width: 37px;
		}

	.orders-items--first,
	.orders-items--second,
	.orders-items--third {
		align-items: center;
	}

	.orders-items--first {
		width: 32%;
	}

	.orders-items--second {
		width: 36%;
	}

	.orders-items--third {
		width: 32%;
	}

	.orders-items--status {
		justify-content: center;
		width: 26%;
	}

	.orders-items--status.is-paid .icon {
		background-image: url("./../assets/icon-label-check.svg");
	}

	.orders-items--status.is-not-paid .icon {
		background-image: url("./../assets/icon-label-error.svg");
	}

	.orders-items--code {
		padding-left: 2%;
		width: 72%;
	}

	.orders-items--payment-method {
		justify-content: center;
		width: 18%;
	}

	.orders-items--payment-method.is-ticket .icon {
		background-image: url("./../assets/icon-bar-codel.svg");
	}

	.orders-items--payment-method.is-debit-card .icon {
		background-image: url("./../assets/icon-debit-card.svg");
	}

	.orders-items--payment-method.is-credit-card .icon {
		background-image: url("./../assets/icon-credit-card.svg");
	}

	.orders-items--amount {
		width: 34%;
	}

	.orders-items--amount .bullet {
		padding: 0 5px;
	}

	.orders-items--updated {
		width: 48%;
	}

	.orders-items--customer {
		width: 100%;
	}

	.orders-items--customer.mask:after {
		right: 10px;
	}

	.customer {
		position: relative;
		width: 100%;
	}

	.customer.border {
		border-left: 1px dashed #cfcfcf;
		padding-left: 16px;
	}

	.customer__type {
		background-image: linear-gradient(134deg, #3023AE 0%, #C96DD8 100%);
		border-radius: 50%;
		color: #FFF;
		display: block;
		float: left;
		font-size: 14px;
		font-weight: 400;
		height: 32px;
		letter-spacing: -.3px;
		line-height: 15px;
		margin-right: 6px;
		padding: 9px 2px;
		text-align: center;
		text-transform: uppercase;
		width: 32px;
	}

	.customer__fullname,
	.customer__email {
		display: block;
		font-size: 14px;
		line-height: 15px;
	}

	.customer__fullname {
		margin-bottom: 2px;
		font-weight: 700;
	}

	.customer__email {
		font-weight: 400;
	}

	@media all and (max-width: 800px) {
		.orders-items .mask:after {
			content: none;
		}

		.orders-items--first,
		.orders-items--second,
		.orders-items--third,
		.orders-items--customer {
			width: 100% !important;
		}

		.orders-items--first,
		.orders-items--second {
			margin-bottom: 10px;
		}

			.orders-items__item {
				border-radius: 3px;
				height: 124px;
				padding: 12px;
			}

			.orders-items__row {
				flex-flow: column nowrap;
			}

			.orders-items__col {
				word-break: normal;
			}

		.orders-items--status,
		.orders-items--payment-method {
			justify-content: inherit;
			width: 10%;
		}

		.orders-items--code {
			padding-left: 0;
			width: 90%;
		}

		.orders-items--amount {
			width: auto;
		}

		.orders-items--updated {
			width: auto;
		}

		.orders-items--customer .orders__link {
			padding-left: 0;
		}

		.customer.border {
			border-left: none;
			border-top: 1px dashed #cfcfcf;
			padding-left: 0;
			padding-top: 10px;
		}

			.customer__type {
				font-size: 12px;
				height: 26px;
				margin-top: 2px;
				margin-right: 8px;
				padding: 5px 2px;
				width: 26px;
			}

			.customer__fullname {
				margin-bottom: 0;
			}
	}
</style>
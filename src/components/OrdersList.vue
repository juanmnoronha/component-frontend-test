<template>
	<div class="orders-list">
		<div class="container">
			<orders-result></orders-result>
			<orders-table></orders-table>
		</div>
	</div>
</template>

<script>
	import OrdersResult from './OrdersResult'
	import OrdersTable from './OrdersTable'

	export default {
		name: 'orders-list',
		components: {
			'orders-result' : OrdersResult,
			'orders-table' : OrdersTable
		}
	}
</script>

<style scoped>
	.orders-list {
		background-image: linear-gradient(149deg, #24C6DC 0%, #009BDE 100%);
		margin: 20px 0 0;
		position: relative;
		width: 100%;
	}

	.orders-list:before {
		background: #FFF url("./../assets/icon-arrow.svg") no-repeat center center;
		border-radius: 50%;
		box-shadow: 0 1px 2px 0 rgba(28,68,140,0.50), 0 4px 4px 0 rgba(28,68,140,0.50), 0 8px 8px 0 rgba(28,68,140,0.50), 0 16px 16px 0 rgba(28,68,140,0.50), 0 32px 32px 0 rgba(28,68,140,0.50);
		content: "";
		display: block;
		font-size: 24px;
		font-weight: 700;
		height: 51px;
		left: 50%;
		margin: 0 auto;
		position: absolute;
		text-align: center;
		top: -20px;
		transform: translateX(-50%);
		width: 51px;
	}

	@media all and (max-width: 800px) {
		.orders-list {
			margin-top: 27px;
		}

		.orders-list:before {
			top: -27px;
		}
	}
</style>
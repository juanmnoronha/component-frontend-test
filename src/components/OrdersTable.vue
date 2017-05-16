<template>
	<div class="orders-table">
		<div class="orders">
			<orders-head></orders-head>
			<orders-items></orders-items>
		</div>
	</div>
</template>

<script>
	import OrdersHead from './OrdersHead'
	import OrdersItems from './OrdersItems'

	export default {
		name: 'orders-table',
		components: {
			'orders-head' : OrdersHead,
			'orders-items' : OrdersItems
		}
	}
</script>

<style scoped>
	.orders-table {
		padding: 32px 0;
		position: relative;
		width: 100%;
	}

	@media all and (max-width: 800px) {
		.orders-table {
			padding: 0;
		}
	}
</style>
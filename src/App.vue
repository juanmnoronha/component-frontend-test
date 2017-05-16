<template>
	<div id="app">
		<orders-list></orders-list>
	</div>
</template>

<script>
	import OrdersList from './components/OrdersList'

	export default {
		name: 'app',
		components: {
			'orders-list' : OrdersList,
		}
	}
</script>

<style>
	@import url('https://fonts.googleapis.com/css?family=Quicksand:300,400,500,700');

	*,
	*:after,
	*::before {
	  transition: all .2s ease;
	}

	* {
		box-sizing: border-box;
	}

	body {
		font-family: 'Quicksand', sans-serif;
		margin: 0;
	}

	p {
		margin: 0;
	}

	.show-for-mobile {
		display: none !important;
	}

	.hide-for-mobile {
		display: show !important;
	}

	.container {
		margin: 0 auto;
		padding: 26px 0 90px;
		width: 800px;
	}
	
	@media all and (max-width: 800px) {
		.container {
			padding: 0 15px 115px;
			width: 100%;
		}

		.show-for-mobile {
			display: block !important;
		}

		.hide-for-mobile {
			display: none !important;
		}
	}
</style>
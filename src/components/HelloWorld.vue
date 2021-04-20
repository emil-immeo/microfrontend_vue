<template>
	<article class="side-menu">
		<ul>
			<li>Home</li>
			<li>About</li>
			<li>Products</li>
			<li>Contact</li>
		</ul>
		{{count}}
	</article>
</template>

<script>
export default {
	name: 'HelloWorld',
	data: () => (
		{
			count: window.pdp.cart.count,
		}
	),
	mounted() {
		console.log(window.pdp)
		window.addEventListener('cartChange', () => {
			this.count = window.pdp.cart.addToCart();
		});
	}
}
</script>

<style>
	.side-menu {
		width: 250px;
		height: 100vh;
		background-color: antiquewhite;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.side-menu ul {
		padding-left: 0;
		margin: 0;
	}

	.side-menu li {
		cursor: pointer;
		margin: 2rem 0;
		list-style-type: none;
		font-size: 1.5rem;
	}

</style>

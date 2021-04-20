<template>
	<article class="my-basket__container">
		<div class="my-basket__svg">
			<svg version="1.1" viewBox="0 0 261.76 226.69" xmlns="http://www.w3.org/2000/svg"><g transform="matrix(1.3333 0 0 -1.3333 -76.311 313.34)"><g transform="translate(178.06 235.01)"><path d="m0 0-22.669-39.264-22.669 39.264h-75.491l98.16-170.02 98.16 170.02z" fill="#41b883"/></g><g transform="translate(178.06 235.01)"><path d="m0 0-22.669-39.264-22.669 39.264h-36.227l58.896-102.01 58.896 102.01z" fill="#34495e"/></g></g></svg>
		</div>
		<h1>My basket</h1>
		<template v-for="(item, index) in myBasket">
			<article :key="index" class="my-basket__item">
				ProductID : {{item.productId}}
			</article>
		</template>
	</article>
</template>

<script>
export default {
	name: 'HelloWorld',
	data: () => (
		{
			myBasket: []
		}
	),
	mounted() {
		window.addEventListener('an-event-name', evt => {
			this.myBasket.push(evt.detail)
		})
	}
}
</script>

<style>
	.my-basket__container {
		border-right: 5px dashed #35495e;
		color: #35495e;
		padding-top: 6rem;
		padding-bottom: 6rem;
		width: 50vw;
		min-height: 100vh;
		height: 100%;
		background-color: white
	}

	.my-basket__svg {
		margin-left: 2.5rem;
		height: 50px;
		width: 50px;
	}

	.my-basket__container h1 {
		margin-left: 1rem;
	}

	.my-basket__item {
		margin: 1rem;
		box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
		background-color: #42b883;
		padding: 3rem;
		border-radius: 8px;
	}


</style>

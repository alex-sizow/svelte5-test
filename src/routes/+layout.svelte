<header>
	<h1><a href="/">Webduck</a></h1>
	<nav>
		<a href="/shop">Shopping cart</a>
		<a href="/todo">Todo</a>
	</nav>
</header>

<main>
	<slot />
</main>

<style scoped>
	header {
		width: 100%;
		min-height: 50px;
		background-color: black;
		padding: 0 13px;
		border-radius: 0 0 30px 30px;
		color: white;
		display: flex;
		align-items: center;
		justify-content: space-between;
		h1 {
			color: yellow;
			font-size: 20px;
		}

		nav {
			a {
				margin-left: 20px;
			}
		}
	}
</style>

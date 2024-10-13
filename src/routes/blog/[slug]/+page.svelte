<script context="module">
	export async function load({ params }) {
		const { id } = params;
		// Здесь вы можете загрузить данные для поста с данным id
		// Например, сделать запрос к API или базе данных
		const post = {
			id,
			title: `Пост номер ${id}`,
			description: `Описание поста номер ${id}`,
			imageUrl: `https://example.com/image${id}.jpg`
		};
		return { props: { post } };
	}
</script>

<script>
	export let post;
</script>

<div class="post">
	<h1>{post.title}</h1>
	<p>{post.description}</p>
	<img src={post.imageUrl} alt={post.title} />
</div>

<style>
	.post {
		margin: 20px;
	}
</style>

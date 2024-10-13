<script>
	import Card from '@/components/blog/Card.svelte';

	const blogPosts = [
		{
			id: 1,
			title: 'Первый пост',
			description: 'Это описание первого поста.',
			imageUrl: 'https://example.com/image1.jpg'
		},
		{
			id: 2,
			title: 'Второй пост',
			description: 'Это описание второго поста.',
			imageUrl: 'https://example.com/image2.jpg'
		},
		{
			id: 3,
			title: 'Третий пост',
			description: 'Это описание третьего поста.',
			imageUrl: 'https://example.com/image3.jpg'
		}
	];
</script>

<div class="blog-list">
	{#each blogPosts as post}
		<a href={`/blog/${post.id}`} class="card-link">
			<Card title={post.title} description={post.description} imageUrl={post.imageUrl} />
		</a>
	{/each}
</div>

<style>
	.blog-list {
		width: 100%;
		margin-top: 40px;
		padding: 0 13px;
		display: flex;
		gap: 20px;
	}
</style>

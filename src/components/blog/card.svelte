<script>
	export let title;
	export let description;
	export let imageUrl;
</script>

<article class="blog-card">
	<img src={imageUrl} alt={title} class="card-image" />
	<div class="card-content">
		<h2 class="card-title">{title}</h2>
		<p class="card-description">{description}</p>
	</div>
</article>

<style>
	.blog-card {
		max-width: 340px;
		aspect-ratio: 1 / 1;
		border: 1px solid #ddd;
		border-radius: 8px;
		overflow: hidden;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
		transition: box-shadow 0.3s ease;
	}

	.card:hover {
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
	}

	.card-image {
		width: 100%;
		height: auto;
	}

	.card-content {
		padding: 16px;
	}

	.card-title {
		font-size: 1.5em;
		margin: 0 0 8px;
	}

	.card-description {
		font-size: 1em;
		color: #666;
	}
</style>

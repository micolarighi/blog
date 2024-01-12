<script>
	export let data;

	$: ({ nodes } = data);
</script>

<div class="bg-gradient-to-b from-blue-800 to-gray-900 p-12">
	<h1 class="text-4xl font-bold">Blog Micola Arighi</h1>
	<h4 class="text-x">Tempat nulis yang penting dan ga penting.</h4>

	<div class="mt-12">
		<h1 class="text-3xl italic">Post Terbaru</h1>
		<div class="grid-cols-3">
			{#each nodes as { title, number, slug }}
				<div class="border my-4 p-4 rounded">
					<a href="/article/{slug}-{number}">{title}</a>
				</div>
			{/each}
		</div>
	</div>
</div>

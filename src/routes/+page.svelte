<script>
	export let data;

	$: ({ nodes } = data);
	import { goto } from '$app/navigation';

	import Footer from './components/Footer.svelte';
</script>

<div class="bg-gradient-to-b from-blue-800 via-blue-900 to-gray-900 px-12 py-10">
	<h1 class="text-4xl font-bold">Blog Micola Arighi</h1>
	<h4 class="text-x">Tempat nulis yang penting dan ga penting.</h4>
</div>
<div class="bg-gray-900 px-12 py-4">
	<h1 class="text-3xl italic mb-4">Post Terbaru</h1>
	<div class="grid grid-cols-3 gap-4">
		{#each nodes as { title, number, slug, publishedAt }}
			<!-- svelte-ignore a11y-no-static-element-interactions -->
			<!-- svelte-ignore a11y-click-events-have-key-events -->
			<button
				class="border p-4 rounded font-bold bg-gray-800 cursor-pointer"
				on:click={goto(`/article/${slug}-${number}`)}
			>
				<button class="text-xl">{title}</button>
				<h3 class="text-sm text-gray-300">{publishedAt.slice(0, 10)}</h3>
			</button>
		{/each}
	</div>
</div>

<Footer />

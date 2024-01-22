<script>
	export let data;

	$: ({ nodes } = data);
	import { goto } from '$app/navigation';

	import Footer from './components/Footer.svelte';
</script>

<div class="min-h-screen bg-gradient-to-tr from-gray-900 from-80% via-blue-900 to-blue-800">
	<div class="px-12 py-10 text-center">
		<h1 class="md:text-6xl text-4xl font-bold">Blog Micola Arighi</h1>
		<h4 class="md:text-2xl text-md">
			<span class="text-blue-500">Tempat nulis</span> yang penting dan ga penting.
		</h4>
	</div>
	<div class="md:px-24 px-12 py-4">
		<h1 class="text-2xl italic mb-4">Post Terbaru</h1>
		<div class="grid md:grid-cols-4 grid-cols-1 gap-4">
			{#each nodes as { title, number, slug, publishedAt }}
				<!-- svelte-ignore a11y-no-static-element-interactions -->
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<button
					class="border p-4 rounded font-bold backdrop-blur-3xl bg-white/10 cursor-pointer hover:bg-gray-700 transition ease-in-out"
					on:click={goto(`/article/${slug}-${number}`)}
				>
					<button class="md:text-xl text-md leading-tight">{title}</button>
					<h3 class="text-sm font-medium text-gray-300">{publishedAt.slice(0, 10)}</h3>
				</button>
			{/each}
		</div>
	</div>

	<Footer />
</div>

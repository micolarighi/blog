<script>
	export let data;

	$: ({ nodes } = data);
	import { goto } from '$app/navigation';

	import Footer from './components/Footer.svelte';
	import Porfolio from './components/Portfolio.svelte';
</script>

<div class="min-h-screen bg-gradient-to-tr from-gray-900 from-80% via-blue-900 to-blue-800">
	<div class="px-12 pt-12 text-center">
		<h1 class="md:text-6xl text-4xl font-bold">Micola Arighi</h1>
		<h4 class="md:text-2xl text-lg leading-tight mt-2">
			Seorang pemuda yang <span class="text-blue-400">hobi ngoding & suka sharing</span>
		</h4>
	</div>
	<Porfolio />
	<div class="md:px-24 px-12 py-12">
		<h1 class="text-2xl italic mb-4">Post Terbaru</h1>
		<div class="grid md:grid-cols-4 grid-cols-1 gap-4">
			{#each nodes as { title, number, slug, publishedAt }}
				<!-- svelte-ignore a11y-no-static-element-interactions -->
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<button
					class="border p-2 rounded font-bold backdrop-blur-3xl bg-white/10 cursor-pointer hover:bg-gray-700 transition ease-in-out"
					on:click={goto(`/article/${slug}-${number}`)}
				>
					<button class="md:text-md text-md leading-tight">{title}</button>
					<h3 class="text-sm font-medium text-gray-300">{publishedAt.slice(0, 10)}</h3>
				</button>
			{/each}
		</div>
	</div>

	<Footer />
</div>

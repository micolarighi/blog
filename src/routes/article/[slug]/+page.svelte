<script>
	export let data;
	import './style.css';
	import { goto } from '$app/navigation';

	import 'iconify-icon';

	const gotoHome = () => {
		goto('/');
	};

	$: ({ discussion } = data);
</script>

<div class="bg-gray-900 md:px-48 px-8 py-6 min-h-screen">
	<button class="text-white bg-gray-600 rounded-full px-2 pt-1 mb-6 text-xl" on:click={gotoHome}
		><iconify-icon icon="mdi:arrow-left"></iconify-icon>
	</button>
	<h1 class="text-4xl font-bold">{discussion.title}</h1>
	<div class="flex gap-3 text-gray-400">
		<h3 class="italic">Oleh Micola Arighi</h3>
		<h3>•</h3>
		<h3 class="italic">{discussion.publishedAt.slice(0, 10)}</h3>
	</div>
	<div class="border-b mt-5"></div>
	<div class="mt-5 blog-content">
		{@html discussion.bodyHTML}
	</div>
</div>

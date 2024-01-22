<script>
	import '../app.css';
	import { Jumper } from 'svelte-loading-spinners';
	import { navigating } from '$app/stores';
</script>

{#if $navigating}
	<div class="w-screen h-screen flex justify-center items-center bg-gray-900">
		<Jumper size="100" color="#3b82f6" unit="px" duration="0.5s" />
	</div>
{/if}

<div class="text-white">
	<slot />
</div>

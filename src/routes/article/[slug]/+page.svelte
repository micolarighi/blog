<script>
	export let data;

	$: ({ discussion } = data);
</script>

<h1 class="text">{discussion.title}</h1>

<div class="bg-gray-800">
	{@html discussion.bodyHTML}
</div>

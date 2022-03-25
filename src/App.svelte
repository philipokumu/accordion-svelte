<script>
	import Item from './components/item.svelte';
	import { dummyItems } from './components/data'
</script>

<main class="container flex justify-center items-center">
	<div class="border bg-gray-50 rounded w-3/4 items-center justify-center">

		<div class="m-6 bg-white">
			{#each dummyItems as item}
			<Item item={item} dummyItemsCount = {dummyItems.length}/>
			{/each}
		  </div>
	</div>
</main>
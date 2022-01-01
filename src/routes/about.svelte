<script context="module">
	import { browser } from '$app/env';
	import { page } from '$app/stores';
	import { onMount } from 'svelte';

	export const load = async ({ url, fetch }) => {
		console.log(url);
		console.log('from load........');
		let response = await fetch('https://jsonplaceholder.typicode.com/todos');
		let final = await response.json();
		console.log(final);

		return {
			props: {
				final: final
			}
		};
	};
</script>

<script>
	export let final;
	let name = 'al razy';

	console.log('from normal');

	onMount(() => {
		console.log('from onmount........');
	});
	let myValue = 10;
</script>

{#each final as item}
	{item?.title}
    <br>
{/each}

.........
{myValue}
<input type="text" bind:value={myValue} />

this is about{name}

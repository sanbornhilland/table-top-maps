<script lang="ts">
	import type { HTMLSelectAttributes } from 'svelte/elements';

	interface $$Props extends Omit<HTMLSelectAttributes, 'type'> {}

	export let value = '';
</script>

<select class="border-2 border-black h6 px-2 py-1" {...$$props} bind:value>
	<slot />
</select>

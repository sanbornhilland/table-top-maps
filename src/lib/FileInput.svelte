<script lang="ts">
	import type { HTMLInputAttributes } from 'svelte/elements';

	interface $$Props extends Omit<HTMLInputAttributes, 'type'> {}
</script>

<input type="file" class="border-2 border-black h6 px-2 py-1" {...$$restProps} on:input />

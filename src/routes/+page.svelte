<script lang="ts">
	import FileInput from '$lib/FileInput.svelte';
	import Header from '$lib/Header.svelte';
	import Select from '$lib/Select.svelte';
	import TextInput from '$lib/TextInput.svelte';

	let source: string = 'web';
	let file: string;
</script>

<Header>
	<TextInput placeholder="Event Name" />
	<div>Map Source</div>
	<Select name="map-source" bind:value={source}>
		<option value="web"> Web </option>
		<option value="upload"> Upload </option>
	</Select>
	{#if source === 'upload'}
		<FileInput
			accept="video/*"
			on:input={(event) => {
				if (!event.currentTarget) {
					return;
				}

				// @ts-expect-error
				file = URL.createObjectURL(event.currentTarget.files[0]);
			}}
		/>
	{:else}
		<TextInput />
	{/if}
</Header>

{#if file}
	<video src={file} autoplay />
{/if}

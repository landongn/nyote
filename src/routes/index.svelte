<style>
	
</style>

<script>
	import marked from "marked";
	import {dialog} from "electron";
	let editBox = '';
	let is_editing = false;
	const new_page = () => {
		is_editing = !is_editing;
	}	

	const save_document = () => {
		fs.mkdirSync("nyote")
		dialog.showSaveDialogSync({title: "Save New Note as..."})
	}
</script>

<svelte:head>
	<title>NYote: Index</title>
</svelte:head>

<section class="container">
	<section class="sidebar"></section>
	<section class="empty_page"></section>
	{#if is_editing}
		<textarea bind:value={editBox} placeholder="edit notes into this box" />
		<button on:click="{save_document}">save</button>
		<section class="markdown">{@html marked(editBox)}</section>
	{/if}
	<section class="add_page"><button on:click="{new_page}">+</button></section>
</section>


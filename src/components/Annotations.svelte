<script>
	import CharRectangle from './CharRectangle.svelte';
	import { rectangles, currentLine } from '../stores/annotationsstore.js';
</script>

<style>
	hr {
		position: absolute;
		width: 100%;
	}

	div {
		position: absolute;
		width: 100%;
		height: 50px;
		background-color: gray;
		opacity: 0.5;
	}
</style>


<hr style="top: {$currentLine.bottom}px" />
{#each $currentLine.rectangles as rectangle, i}
	<CharRectangle {...rectangle} idx={i} />
{/each}

<div id="overlay" style="top: {$currentLine.bottom-50}px" >
</div>

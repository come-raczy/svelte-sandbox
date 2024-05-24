<script lang="ts">
	import '@fontsource/luckiest-guy';
	import LeftSide from 'components/LeftSide.svelte';
	let theme = 'dark';
	import { count } from '$lib/stores';
</script>

<div style="flex-basis: 100%;height: 0"></div>
<div class="app {theme}">
	<div class="header">
		<p>the count is: {$count}</p>
	</div>
	<div style="flex-basis: 100%;height: 0"></div>
	<LeftSide />
	<div class="main">
		<slot />
	</div>
	<div class="rightSide"></div>
	<div style="flex-basis: 100%;height: 0"></div>
	<div class="footer"></div>
</div>

<style>
	@import '../app.css';

	:global(body) {
		font-family: 'Luckiest Guy', system-ui;
	}

	div.app {
		display: flex;
		flex-wrap: wrap;
		width: 100vw;
		max-width: 100%;
		justify-content: space-between;
		height: 100%;
		margin: 0;
		padding: 0;
	}
	div.header {
		height: 5vh;
		width: 100%;
		border: 5px solid var(--color-primary);
	}
	div.leftSide {
		min-height: 10vh;
		width: 15%;
		border: 5px solid green;
	}
	div.main {
		width: 70%;
		justify-content: center;
		align-items: center;
		margin: 0;
		border: 5px solid red;
	}
	div.rightSide {
		flex-grow: 1;
		min-height: 10vh;
		margin: 0;
		padding: 0;
		border: 5px solid yellow;
	}
	div.footer {
		height: 5vh;
		width: 100%;
		border: 5px solid black;
	}
</style>

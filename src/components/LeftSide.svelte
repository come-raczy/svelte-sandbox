<script lang="ts">
	import { count } from '$lib/stores';
</script>

<div class="leftSide">
	<p>count: {$count}</p>
</div>

<style>
	div.leftSide {
		min-height: 10vh;
		width: 15%;
		border: 5px solid green;
	}
</style>

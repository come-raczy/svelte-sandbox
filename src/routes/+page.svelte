<script>
    //import { theme } from '$lib/theme';
    //import { color } from '$lib/variables';
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<h2>Example of variables and mixins preprocessed by scss</h2>
<p class="local">This is a local scoped style</p>

<style lang="scss">
    h2 {
        color: $color;
    }

.local {
    color: var(--color-primary);
}

</style>

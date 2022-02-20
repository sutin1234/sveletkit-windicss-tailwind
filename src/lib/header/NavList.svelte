<script>
	export let items = ['Dashboard', 'Team', 'Projects', 'Calendar', 'Reports'];
</script>

{#each items as item}
	<a href="#" class="*navMenu" aria-current="page">{item}</a>
{/each}

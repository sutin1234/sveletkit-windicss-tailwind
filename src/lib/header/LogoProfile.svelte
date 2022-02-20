<script>
	export let imgUrl =
		'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80';
	export let alt = 'Workflow';
</script>

<img class={$$props.class ?? 'h-8 w-8 rounded-full'} src={imgUrl} {alt} />

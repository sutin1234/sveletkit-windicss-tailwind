<script>
	export let imgUrl = 'https://tailwindui.com/img/logos/workflow-mark-indigo-500.svg';
	export let alt = 'Workflow';
</script>

<img class={$$props.class ?? 'h-8 w-8'} src={imgUrl} {alt} />

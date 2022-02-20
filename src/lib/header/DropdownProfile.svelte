<script>
	// @ts-nocheck

	import LogoProfile from './LogoProfile.svelte';
	import classes from 'svelte-transition-classes';

	import { clickOutside } from '$lib/clickOutside';
	let isToggle = false;
	function toggle() {
		isToggle = !isToggle;
	}
	function handleClickOutside() {
		isToggle = false;
	}
</script>

<div class="ml-3 relative">
	<div>
		<button
			on:click={toggle}
			use:clickOutside
			on:click_outside={handleClickOutside}
			type="button"
			class="max-w-xs bg-gray-800 rounded-full flex items-center text-sm focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white"
		>
			<span class="sr-only">Open user menu</span>
			<LogoProfile />
		</button>
	</div>
	{#if isToggle}
		<div
			in:classes={{
				duration: 100,
				base: 'transition ease-out duration-100',
				from: 'transform opacity-0 scale-95',
				to: 'transform opacity-100 scale-100'
			}}
			out:classes={{
				duration: 75,
				base: 'transition ease-in duration-75',
				from: 'transform opacity-100 scale-100',
				to: 'transform opacity-0 scale-95'
			}}
			class="*menuProfile"
		>
			<a href="#" class="block px-4 py-2 text-sm text-gray-700">Your Profile</a>

			<a href="#" class="block px-4 py-2 text-sm text-gray-700">Settings</a>

			<a href="#" class="block px-4 py-2 text-sm text-gray-700">Sign out</a>
		</div>
	{/if}
</div>

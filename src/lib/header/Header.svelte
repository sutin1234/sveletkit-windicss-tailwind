<script>
	import Logo from './Logo.svelte';
	import NavList from './NavList.svelte';
	import Notification from './Notification.svelte';
	import DropdownProfile from './DropdownProfile.svelte';
	import MenuIcon from './MenuIcon.svelte';
	import CloseIcon from './CloseIcon.svelte';
	import NavListVertical from './NavListVertical.svelte';

	let isShow = false;
	function isToggle() {
		isShow = !isShow;
	}
</script>

<div class="min-h-full">
	<nav class="bg-gray-800">
		<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
			<div class="flex items-center justify-between h-16">
				<div class="flex items-center">
					<div class="flex-shrink-0">
						<!-- Nav List -->
						<Logo />
					</div>
					<div class="hidden md:block">
						<div class="ml-10 flex items-baseline space-x-4">
							<!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
							<NavList />
						</div>
					</div>
				</div>
				<div class="hidden md:block">
					<div class="ml-4 flex items-center md:ml-6">
						<!-- Notification  bell -->
						<Notification />

						<!-- Profile dropdown -->
						<DropdownProfile />
					</div>
				</div>
				<div class="-mr-2 flex md:hidden">
					<!-- Mobile menu button -->
					<button
						type="button"
						on:click={isToggle}
						class="bg-gray-800 inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white"
						aria-controls="mobile-menu"
						aria-expanded="false"
					>
						<span class="sr-only">Open main menu</span>
						<!-- hambeger button -->
						{#if !isShow}
							<MenuIcon />
						{:else}
							<!-- close button -->
							<CloseIcon />
						{/if}
					</button>
				</div>
			</div>
		</div>

		{#if isShow}
			<!-- Mobile menu, show/hide based on menu state. -->
			<div class="md:hidden" id="mobile-menu">
				<div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
					<NavListVertical />
				</div>
				<div class="pt-4 pb-3 border-t border-gray-700">
					<div class="flex items-center px-5">
						<div class="flex-shrink-0">
							<img
								class="h-10 w-10 rounded-full"
								src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
								alt=""
							/>
						</div>
						<div class="ml-3">
							<div class="text-base font-medium leading-none text-white">Tom Cook</div>
							<div class="text-sm font-medium leading-none text-gray-400">tom@example.com</div>
						</div>
						<button
							type="button"
							class="ml-auto bg-gray-800 flex-shrink-0 p-1 rounded-full text-gray-400 hover:text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white"
						>
							<span class="sr-only">View notifications</span>
							<!-- Heroicon name: outline/bell -->
							<Notification />
						</button>
					</div>
					<div class="mt-3 px-2 space-y-1">
						{#each ['Your Profile', 'Settings', 'Sign out'] as item}
							<a href="#/" class="*menuItem">{item}</a>
						{/each}
					</div>
				</div>
			</div>
		{/if}
	</nav>

	<header class="bg-white shadow">
		<div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
			<h1 class="text-3xl font-bold text-gray-900">Dashboard</h1>
		</div>
	</header>
	<main>
		<div class="max-w-7xl mx-auto py-6 sm:px-6 lg:px-8">
			<!-- Replace with your content -->
			<div class="px-4 py-6 sm:px-0">
				<div class="border-4 border-dashed border-gray-200 rounded-lg h-96" />
			</div>
			<!-- /End replace -->
		</div>
	</main>
</div>

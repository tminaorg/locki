<script lang="ts">
	export let title = '';
	export let description = '';
	export let featuredImage = '';
</script>

<svelte:head>
	<title>{title} | Locki</title>
</svelte:head>

<article id="blog-{title}">
	<header class="mb-4 bg-primary-600">
		<span class="py-96">
			<h1 class="pt-16 text-6xl font-black text-center dark:text-white">
				{title}
			</h1>
			{#if featuredImage !== ''}
				<div class="max-w-4xl mx-auto mt-8 mb-2">
					<div class="px-6">
						<img
							src={featuredImage}
							class="max-h-80 mx-auto object-fill overflow-hidden rounded-lg shadow-lg ring-4 ring-zinc-300/40 dark:ring-gray-900/40 shadow-neutral-100/20 dark:shadow-neutral-800/40"
							alt={title}
						/>
					</div>
				</div>
			{/if}
			{#if description !== ''}
				<h2 class="text-lg text-center max-w-2xl px-6 pt-6 pb-6 mx-auto dark:text-white">
					{description}
				</h2>
			{/if}
		</span>
	</header>
	<div
		class="prose-xl dark:prose-invert prose-a:text-blue-800 dark:prose-a:text-blue-200 hover:prose-a:underline sm:text-justify max-w-7xl px-6 pt-6 pb-16 mx-auto dark:text-white"
	>
		<slot />
	</div>
</article>

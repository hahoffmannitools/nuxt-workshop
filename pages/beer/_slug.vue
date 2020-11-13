<template>
	<div class="p-3">
		<h1 class="text-2xl mb-3">{{ beer.title }}</h1>
		<img class="mb-8" :src="beer.image_url" />
		<p class="mb-3">{{ beer.description }}</p>
		<NuxtContent :document="beer" class="prose prose-sm sm:prose lg:prose-lg xl:prose-2xl mx-auto"/>
		<NuxtLink class="btn btn-outline mt-10" to="/beers">Back to Beers</NuxtLink>
	</div>
</template>

<script>
	export default {
		async asyncData({ $content, params }) {
			console.log(params);
			const beer = await $content('beer', params.slug).fetch()
			return { beer }
		}
	}
</script>
<template>
	<div class="p-3">
		<img class="mb-8" :src="river.image" />
        <h1 class="text-2xl mb-3">{{ river.title }}</h1>
        <p class="mb-3">{{ river.description }}</p>
        <p class="mb-3">{{ river.continent }}</p>

		<!-- <pre>{{ river }}</pre> -->
		<NuxtLink class="btn btn-outline mt-3" to="/rivers-fetch">Back to Rivers</NuxtLink>
	</div>
</template>

<script>
	export default {
		async asyncData({$axios, params}) {
			const river = await $axios.$get(`https://api.nuxtjs.dev/rivers/${params.slug}`);
			return { river }
		},
	}
</script>

<style lang="scss" scoped>

</style>
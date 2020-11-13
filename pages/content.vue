<template>
	<div>
		{{ page.title }}
		{{ page.description }}
		<NuxtContent :document="page" />
	</div>
</template>

<script>
	export default {
		async asyncData({ $content, params }) {
			// const page = await $content('hello').fetch()
			const page = await $content('articles', 'hello2').fetch()
			return { page }
		}
	}
</script>
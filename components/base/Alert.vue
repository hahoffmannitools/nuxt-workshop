<template>
	<div class="fixed top-0 right-0 bottom-0 left-0 z-50 overflow-auto bg-smoke-light flex">
		<div class="relative p-8 bg-white w-full max-w-md m-auto flex-col flex">
			Crazy lazy Alert!
			<button class="btn btn-blue" @click="handleCloseClick">Close Alert</button>
		</div>
	</div>
</template>

<script>
export default {
	name: "Alert",
	methods: {
		handleCloseClick() {
			this.$emit('closeAlert');
		}
	}
}
</script>

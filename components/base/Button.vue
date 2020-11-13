<template>
	<div>
		<button class="btn btn-blue" @click="handleClick()">Open Lazy Alert</button>
	</div>
</template>

<script>
export default {
	methods: {
		handleClick() {
			this.$emit('buttonClick');
		}
	}
}
</script>
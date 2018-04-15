<template>
	<div class="contact">

			<img class="pic" v-bind:src="url" alt="Animal">
			<p>{{ title }}</p>
			<p>{{ year }}</p>
	</div>
</template>

<script>
	export default {
		props: ['url', 'title', 'year']
	}
</script>

<style scoped>
		.contact {
			background-color: white;
			border: 2px solid #E5E5E7;
			min-height: 30px;
			width: 100%;
		}
		img {
			width: 100px;
			height: auto;
		}

</style>

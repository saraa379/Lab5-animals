<template>
	<div class="wrap">

			<img class="pic" v-bind:src="urlCh" alt="Animal">
			<div class="textChosen">
					<p class="name">{{ titleCh }}</p>
					<p>{{ descCh }}</p>
			</div>
	</div>
</template>

<script>
	export default {
		props: ['urlCh', 'titleCh', 'descCh']
	}
</script>

<style scoped>
		.wrap {
			background-color: #585858;
			border: 2px solid #110c11;
			min-height: 30px;
			width: 100%;
			display: flex;
			flex-flow: column wrap;
			color: white;
		}
		img {
			width: 100px;
			height: 100px;
			border: 2px solid #110c11;
		}
		.textChosen {
		}
		.name {
			font-weight: bold;
			font-size: 1.2rem;
		}

</style>

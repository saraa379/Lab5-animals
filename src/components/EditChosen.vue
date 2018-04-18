<template>
	<div class="wrapE">

			<img class="picE" v-bind:src="urlE" alt="Animal">
			<div class="textEdit">
					<p class="name">{{ titleE }}</p>
					<p>{{ descE }}</p>
			</div>
	</div>
</template>

<script>
	export default {
		props: ['urlE', 'titleE', 'descE', 'idE']
	}
</script>

<style scoped>
		.wrapE {
			background-color: #585858;
			min-height: 30px;
			width: 100%;
			display: flex;
			flex-flow: column wrap;
			justify-content: center;
			color: white;
		}
		img {
			width: 100%;
			height: auto;
			border-bottom: 2px solid #110c11;
		}
		.textChosen {
			padding-left: 10px;
		}
		.name {
			font-weight: bold;
			font-size: 1.2rem;
		}

</style>

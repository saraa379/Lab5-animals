<template>
	<div class="wrap">

			<img class="pic" v-bind:src="urlCh" alt="Animal">
			<div class="textChosen">
					<div class="row">
							<p class="name">{{ titleCh }}</p>
							<div v-on:click="editChosen"><i class="fas fa-cog"></i></div>
					</div>
					<p class="lastP">{{ descCh }}</p>
			</div>
	</div>
</template>
<script defer src="https://use.fontawesome.com/releases/v5.0.6/js/all.js"></script>
<script>
	export default {
		props: ['urlCh', 'titleCh', 'descCh', 'idCh'],
		methods: {
			editChosen: function(event) {
					this.$emit('show-edit');
			}
		} //methods
	}
</script>

<style scoped>
		.wrap {
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
			position: relative;
			background-color: #999999;
		}
		.name {
			font-weight: bold;
			font-size: 1.2rem;
			display: inline-block;
			width: 50px;
		}
		i {
			color: white;
			position: relative;
			font-size: 25px;
		}
		p {
			margin: 0;
		}
		.lastP {
			margin-top: 5px;
			margin-bottom: 10px;
		}
		.row {
			display: flex;
			flex-flow: row nowrap;
			justify-content: space-between;
			padding-right: 15px;
			padding-top: 10px;
		}

</style>

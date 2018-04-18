<template>
	<div id="contact" v-bind:class="colorDiv" v-on:click="changeColor">

			<img class="pic" v-bind:src="url" alt="Animal">
			<div class="text">
					<p class="name">{{ title }}</p>
					<p>{{ desc }}</p>
			</div>
	</div>
</template>

<script>
	export default {
		props: ['url', 'title', 'desc', 'idComp', 'colorDiv'],
		data: function() {
				return {
				}
		},
		methods: {
			changeColor: function(event) {
					//this.colorDiv = "backColorChosen";
					//console.log("Id of the component: " + this.idComp);
					this.$emit('send-id', this.idComp);
			}
		} //methods
	}
</script>

<style scoped>
		#contact {
			border: 2px solid #110c11;
			min-height: 30px;
			width: 100%;
			display: flex;
			flex-flow: row nowrap;
			color: white;
		}
		.backColorGrey {
				background-color: #585858;
		}
		.backColorChosen {
				background-color: #999999;
		}
		img {
			width: 100px;
			height: 100px;
			border-right: 2px solid #110c11;
		}
		.text {
			margin-left: 15px;
			padding-top: 10px;
		}
		.name {
			font-weight: bold;
			font-size: 1.2rem;
		}
		p {
			margin-top: 5px;
			margin-bottom: 5px;
		}

</style>

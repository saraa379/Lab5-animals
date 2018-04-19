<template>
	<div class="wrapE">

			<img class="picE" v-bind:src="urlE" alt="Animal">

			<div class="form">
            <label for="name">{{titleE}}</label>
            <input type = "text" name="name" v-model="nameAnimal"/>
            <label for="urlAnimal">Url of a picture</label>
            <input type = "text" name="urlAnimal" v-model="urlAnimal"/>
						<label for="description">{{descE}}</label>
						<textarea name="description" v-model="descAnimal"></textarea>

            <div class="btns">
                <button id="btnCancel" class="btnsEdit" v-on:click="cancel">Cancel</button>
                <button id="btnSave" class="btnsEdit" v-on:click="save">Save</button>
            </div><!--btnProfil-->
      </div>

	</div>
</template>

<script>
	export default {
		props: ['urlE', 'titleE', 'descE', 'idE'],
		data: function() {
			 return {
				 nameAnimal: "",
				 urlAnimal: "",
				 descAnimal: "",
			 };
		 },  // data
		methods: {
			cancel: function(event) {
					this.$emit('cancel-edit');
			},
			save: function(event) {

					this.$emit('save-edit', this.nameAnimal, this.urlAnimal, this.descAnimal);
			}
		} //methods
	}
</script>

<style scoped>
		.wrapE {
			background-color: #999999;
			min-height: 30px;
			width: 100%;
			display: flex;
			flex-flow: column wrap;
			color: white;
		}
		img {
			max-width: 300px;
			height: auto;
			margin: auto;
			border: 2px solid white;
		}
		.name {
			font-weight: bold;
			font-size: 1.2rem;
		}
		.form {
				max-width: 300px;
				margin-top: 10px;
				margin-bottom: 10px;
				margin: auto;
				padding-top: 10px;
			}
			input, textarea {
				 outline: none;
				 transition: .2s all linear;
				 display: flex;
				 padding: 8px;
				 width: 100%;
				 margin: 10px 0;
				 height: 30px;
				 border: 2px solid white;
				 color: #585858;
			}
			label {
				color: white;
				font-size: 1.1rem;
			}
			textarea {
				min-height: 50px;
			}
			.btns {
				width: 100%;
				background-color: transparent;
				display: flex;
				flex-flow: row nowrap;
				justify-content: space-between;
				margin: 0 auto;
			}

				.btnsEdit {
						width: 100px;
						border: 2px solid #585858;
						border-radius: 5px;
						padding-top: 10px;
						padding-bottom: 10px;
						padding-right: 5px;
						padding-left: 5px;
						background-color: #585858;
						color: white;
						font-size: 1.1rem;
						animation-name: fadeIn;
						animation-delay: 2s;
						margin-bottom: 5px;
						margin-top: 10px;
						text-align: center;
				}

</style>

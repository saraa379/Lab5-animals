<template>
	<div class="wrapE">

			<img class="picE" v-bind:src="urlE" alt="Animal">

			<div class="form">
            <label for="name">{{titleE}}</label>
            <input type = "text" name="name" placeholder="Enter animal name" />
            <label for="urlAnimal">Url of a picture</label>
            <input type = "text" name="urlAnimal" placeholder="Enter url"/>
						<label for="description">{{descE}}</label>
						<textarea name="description" placeholder="Enter new description"></textarea>

            <div class="btns">
                <button id="btnCancel" class="btnsEdit">Cancel</button>
                <button id="btnSave" class="btnsEdit">Save</button>
            </div><!--btnProfil-->
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
			background-color: #999999;
			min-height: 30px;
			width: 100%;
			display: flex;
			flex-flow: column wrap;
			justify-content: center;
			color: white;
		}
		img {
			max-width: 300px;
			height: auto;
			margin: auto;
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
				text-align: center;
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

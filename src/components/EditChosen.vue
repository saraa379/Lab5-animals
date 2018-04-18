<template>
	<div class="wrapE">

			<img class="picE" v-bind:src="urlE" alt="Animal">

			<div class="form">
            <label for="name">Animal name</label>
            <input type = "text" name="name" placeholder="Animal name" />
            <label for="urlAnimal">Description</label>
            <input type = "text" name="urlAnimal" placeholder=""/>
						<label for="description">Description</label>
						<textarea name="description" placeholder="Short description"></textarea>

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
			background-color: #585858;
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
			border: 2px solid #110c11;
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

</style>

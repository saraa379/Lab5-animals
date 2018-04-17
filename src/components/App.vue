<template>
  <div id="app">
      <header>
         <p>BEST ANIMAL COMPANIONS</p>
      </header>
      <main>
        <div class="contactList">
            <animal-comp
                v-for="animal in animals"
                v-bind:key="animal.id"
                v-bind:title="animal.title"
                v-bind:desc="animal.desc"
                v-bind:url="animal.url"
                v-bind:colorDiv="colorAnimal"
            ></animal-comp>
        </div>

        <div class="chosenProfile"></div>
      </main>
  </div><!--end of app-->
</template>

<script>
import Animal from './Animal.vue';
import Chosen from './Chosen.vue';

  export default {
      name: 'app',
      components: {
  		    'animal-comp': Animal,
          'chosen-comp': Chosen
  	 },
     data: function() {
    		return {
          animals: [
              { id: 1, title: 'Dog', desc: 'Smart, social and high-energy animal.', url: 'https://pixabay.com/get/e833b60b29f5043ed1534705fb09459fe376e1dc10ac104497f3c87cafecbcb9/dog-1674115_1920.jpg' },
              { id: 2, title: 'Fish', desc: 'Has calming effect, does not require constant attention.', url: 'https://pixabay.com/get/eb30b90828f1063ed1534705fb09459fe376e1dc10ac104497f3c87fa2edb6bb/fish-2587057_1920.jpg' },
              { id: 3, title: 'Rodents', desc: 'Active, small and sociable.', url: 'https://pixabay.com/get/ee30b40a2ef61c22d9584518a34f4f96e274ebdc04b0144396f9c778a4e9bd/guinea-pig-755562_1920.jpg' },
              { id: 4, title: 'Cat', desc: 'Playful, acrobatic and cuddly friends.', url: 'https://pixabay.com/get/ea37b90e2af7033ed1534705fb09459fe376e1dc10ac104497f3c87fa4e8bcbb/cute-3281232_1920.jpg' },
              { id: 5, title: 'Rabbit', desc: 'Adorable and wonderful indoor pet.', url: 'https://pixabay.com/get/ea34b00e2ef6063ed1534705fb09459fe376e1dc10ac104497f3c87fa3e5b7b9/rabbit-3111627_1920.jpg' }
          ],
          colorAnimal: 'backColorGrey'
    		};
    	},  // data
    	methods: {
        makeChosen: function(event) {
						this.colorAnimal = "backColorChosen";
				}
     } //methods
  } //export default
</script>

<!-- CSS libraries -->
<style src="normalize.css/normalize.css"></style>

<!-- Global CSS -->
<style>
  * {
    box-sizing: border-box;
  }
  body {
    height: 100%;
    background-color: #110c11;/*#F5F5F5;*/
    min-width: 200px;
  }

</style>

<!-- Scoped component css -->
<!-- It only affect current component -->
<style scoped>
  #app {
    position: relative;
  }
    header {
      height: 400px;
      background-color: #10ABFE;
      color: white;
      margin: 0;
      position: relative;
      background-image: linear-gradient(
	      	rgba(9, 11, 87, 0.3),
	      	rgba(0, 0, 0, 0.5)
	    	  ),
			   url('img/cover7.jpg');
    	background-position: center 40%;
    	background-repeat: no-repeat;
    	background-size: cover;
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;
    }
      header p {
        margin: 0;
        position: relative;
        font-size: 2.8rem;
        font-family: 'Open Sans', sans-serif;
        text-align: center;
      }
      main {
        width: 90%;
        display: flex;
        flex-flow: row wrap;
        justify-content: flex-start;
        margin: 0 auto;
        padding-bottom: 40px;
      }
      .contactList, .chosenProfile {
        background-color: white;
        flex-basis: 49%;
        min-height: 300px;
     }
     .contactList {
        flex-basis: 51%;
     }
     .chosenProfile {
       flex-basis: 49%;
       background-color: #585858;
       border: 2px solid #110c11;
     }

/*Media queries*/

@media screen and (max-width: 800px){
    header {
      height: 300px;
    }
    header p {
      font-size: 2.2rem;
    }
}/*end of 800*/

@media screen and (max-width: 500px){
  .contactList, .chosenProfile {
     flex-basis: 100%;
   }
   .contactList {
      order: 2;
    }
    .chosenProfile {
      order: 1;
    }
    header {
      height: 250px;
    }
    header p {
      font-size: 1.2rem;
    }
}/*end of 500*/

</style>

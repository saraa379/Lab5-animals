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
                v-bind:idComp="animal.id"
                v-bind:colorDiv="animal.colorAnimal"
                v-on:send-id="recieveId"
            ></animal-comp>
        </div>

        <div class="chosenProfile" v-if="visibleChosen">
          <chosen-comp
              v-bind:key="chosenAnimal.id"
              v-bind:titleCh="chosenAnimal.title"
              v-bind:descCh="chosenAnimal.desc"
              v-bind:urlCh="chosenAnimal.url"
              v-bind:idCh="chosenAnimal.id"
              v-on:show-edit="showEditPage"
          ></chosen-comp>
        </div>
        <div class="chosenProfile" v-else>
          <edit-comp
              v-bind:key="chosenAnimal.id"
              v-bind:titleE="chosenAnimal.title"
              v-bind:descE="chosenAnimal.desc"
              v-bind:urlE="chosenAnimal.url"
              v-bind:idE="chosenAnimal.id"
          ></edit-comp>
        </div>
      </main>
  </div><!--end of app-->
</template>

<script>
import Animal from './Animal.vue';
import Chosen from './Chosen.vue';
import EditChosen from './EditChosen.vue';

  export default {
      name: 'app',
      components: {
  		    'animal-comp': Animal,
          'chosen-comp': Chosen,
          'edit-comp': EditChosen
  	 },
     data: function() {
    		return {
          animals: [
              { id: 1, title: 'Dog', desc: 'Smart, social and high-energy animal.', colorAnimal: 'backColorGrey', url: 'https://pixabay.com/get/e834b30c28f5073ed1534705fb09459fe376e1dc10ac104497f4c17ca6e8b6bc/dog-1123016_1920.jpg' },
              { id: 2, title: 'Fish', desc: 'Has calming effect, does not require constant attention.', colorAnimal: 'backColorGrey', url: 'https://pixabay.com/get/eb3cb30e2cf7013ed1534705fb09459fe376e1dc10ac104497f4c17ca6efbcbd/fish-2921430_1920.jpg' },
              { id: 3, title: 'Rodents', desc: 'Active, small and sociable.', colorAnimal: 'backColorGrey', url: 'https://pixabay.com/get/ec35b10d2df21c22d9584518a34f4f96e274ebdc04b0144391f0c478a0eab2/guinea-pig-500256_1920.jpg' },
              { id: 4, title: 'Cat', desc: 'Playful, acrobatic and cuddly friends.', colorAnimal: 'backColorGrey', url: 'https://pixabay.com/get/eb33b20c2afc023ed1534705fb09459fe376e1dc10ac104497f4c17ca5ecbdba/kitten-with-mom-2633283_1920.jpg' },
              { id: 5, title: 'Rabbit', desc: 'Adorable and wonderful indoor pet.', colorAnimal: 'backColorGrey', url: 'https://pixabay.com/get/ea34b50720f51c22d2524518a34f4f96e274ebdc04b0144391f0c47ba3ecb6/lop-eared-314881_1280.jpg' }
          ],
          chosenId: 0,
          visibleChosen: true,
          visibleEdit: false,
          chosenAnimal: { id: 1, title: 'Dog', desc: 'Smart, social and high-energy animal.', colorAnimal: 'backColorGrey', url: 'https://pixabay.com/get/e834b30c28f5073ed1534705fb09459fe376e1dc10ac104497f4c17ca6e8b6bc/dog-1123016_1920.jpg' }

    		};
    	},  // data
    	methods: {
        recieveId: function(strId) {
						this.chosenId = parseInt(strId);
            //console.log("Id is recieved: " + strId);
            //console.log("Chosen id: " + this.chosenId);
            var i;
            for (i = 0; i < this.animals.length; i++) {
                if (this.animals[i].id == this.chosenId){
                    this.animals[i].colorAnimal = "backColorChosen";
                    this.chosenAnimal.id = this.animals[i].id;
                    this.chosenAnimal.title = this.animals[i].title;
                    this.chosenAnimal.desc = this.animals[i].desc;
                    this.chosenAnimal.url = this.animals[i].url;
                } else {
                  this.animals[i].colorAnimal = "backColorGrey";
                }
                console.log("Animals id: " + this.animals[i].id);
            }//end for
				},
        showEditPage: function(event) {
  				    this.visibleChosen = false;
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

<template>
  <div id="app">
      <header>
         <p>DJURENS BARN</p>
      </header>
      <main>
        <div class="contactList">
            <!--<contact-indiv v-for="url in urlList" v-bind:url="url" v-bind:key="url"></contact-indiv>-->
            <!--<book
                v-bind:key="1"
                v-bind:title="books.title"
                v-bind:year="books.year"
                v-bind:author="author"
                v-bind:url="books.yearurlList[0]"
            ></book> -->
            <animal-comp
                v-for="animal in animals"
                v-bind:key="animal.id"
                v-bind:title="animal.title"
                v-bind:year="animal.year"
                v-bind:url="animal.url"
            ></animal-comp>
        </div>

        <div class="chosenProfile"></div>
      </main>
  </div><!--end of app-->
</template>

<script>
import Animal from './Animal.vue';

  export default {
      name: 'app',
      components: {
  		    'animal-comp': Animal
  	 },
     data: function() {
    		return {
          animals: [
              { id: 1, title: 'The Maze Runner', year: '2009', url: 'https://cdn.pixabay.com/photo/2018/04/11/06/03/flamingo-3309628_640.jpg' },
              { id: 2, title: 'The Scorch Trials', year: '2010', url: 'https://i.pinimg.com/736x/78/b8/a5/78b8a51098ef44932f2c459e23861b61.jpg' },
              { id: 3, title: 'The Death Cure', year: '2011', url: 'https://i.ytimg.com/vi/M9fv8aFhyXU/maxresdefault.jpg' },
              { id: 4, title: 'The Kill Order', year: '2012', url: 'https://img.buzzfeed.com/buzzfeed-static/static/2014-11/5/13/enhanced/webdr07/enhanced-5913-1415212088-2.jpg?downsize=715:*&output-format=auto&output-quality=auto' },
              { id: 5, title: 'The Fever Code', year: '2016', url: 'https://i.ytimg.com/vi/M9fv8aFhyXU/maxresdefault.jpg' }
          ]
    		};
    	},  // data
    	methods: {
    		addImageToList: function(imageUrl) {
    			console.log('addImageToList', imageUrl);
    			this.urlList.push(imageUrl);
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
  }

</style>

<!-- Scoped component css -->
<!-- It only affect current component -->
<style scoped>
  #app {
    position: relative;
  }
    header {
      height: 300px;
      background-color: #10ABFE;
      color: white;
      margin: 0;
      position: relative;
      background-image: linear-gradient(
	      	rgba(9, 11, 87, 0.3),
	      	rgba(0, 0, 0, 0.5)
	    	  ),
			   url('img/cover2.jpg');
    	background-position: center 35%;
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
        font-size: 2rem;
        font-family: 'Open Sans', sans-serif;
        text-align: center;
      }
      main {
        width: 90%;
        display: flex;
        flex-flow: row wrap;
        justify-content: flex-start;
        margin: 0 auto;
      }
      .contactList, .chosenProfile {
        border: 1px solid grey;
        background-color: white;
        flex-basis: 49%;
        min-height: 300px;
     }
     .contactList {
        flex-basis: 51%;
     }
     .chosenProfile {
       flex-basis: 49%;
     }

/*Media queries*/

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
    header p {
      font-size: 1.2rem;
    }
}/*end of 500*/

</style>

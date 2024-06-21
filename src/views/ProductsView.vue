<!-- first letter should always be uppercase -->
 <!-- try to always have two words in the name to help with kebab case -->

 <!-- insert content in the page you created -->
  <!-- add a button to the navbar -->
   <!-- import the products to the router(index.js) -->
   <!-- add a link to the new page in your router(index.js) -->
  <template>
    <div>
        <h1>This is the Products Page</h1>
    </div>
    <div>
        <!-- search bar -->
        <search-bar :books="books"/>
        <h1>Great reads</h1>
        <section>
        <div class="myCard" v-for="book in books" :key="book">

                <h1><product-comp :product-name="book.title"/></h1>
                    <div class="myCoverStyle"><img :src="book.cover"></div>

                <div class="moreInfo">
                    <h5>Author: <product-comp :product-author="book.author"/></h5>
                    <h5>Year: <product-comp :product-year="book.year"/></h5>
                    <h5>Genre: <product-comp :product-genre="book.genre"/></h5>
                    <h5>Pages: <product-comp :product-pages="book.pages"/></h5>
                    <h5>Publisher: <product-comp :product-publisher="book.publisher"/></h5>
                    <h5>ISBN: <product-comp :product-isbn="book.isbn"/></h5>
                </div>
        </div>
        </section>
    </div>

</template>

  <script>
import ProductComp from '../components/ProductComp.vue'
import SearchBar from '../components/SearchBar.vue';

export default{
   components:{
    ProductComp,
    SearchBar,
   },
   data() {
    return {
        books:[
            {title: "The Great Gatsby",
            author: "F. Scott Fitzgerald",
            year: 1925,
            genre: "Literary Fiction",
            pages: 180,
            publisher: "Charles Scribner's Sons",
            isbn: "978-0743273565",
            cover:'https://i0.wp.com/americanwritersmuseum.org/wp-content/uploads/2018/02/CK-3.jpg?resize=267%2C400&ssl=1'
            },
            {title: "To Kill a Mockingbird",
            author: "Harper Lee",
            year: 1960,
            genre: "Southern Gothic",
            pages: 281,
            publisher: "J. B. Lippincott & Co.",
            isbn: "978-0446310789",
            cover:'https://media.glamour.com/photos/56e1f3c462b398fa64cbd304/master/w_1600%2Cc_limit/entertainment-2016-02-18-main.jpg'
            },
            {title: "1984",
            author: "George Orwell",
            year: 1949,
            genre: "Dystopian Fiction",
            pages: 328,
            publisher: "Secker & Warburg",
            isbn: "978-0451524935",
            cover:'https://i0.wp.com/www.printmag.com/wp-content/uploads/2017/01/2a34d8_463ff497abfa4bca9b96d696e911746fmv2.jpeg?resize=500%2C769&quality=89&ssl=1'
            },
            {title: "Pride and Prejudice",
            author: "Jane Austen",
            year: 1813,
            genre: "Romance",
            pages: 279,
            publisher: "Thomas Egerton",
            isbn: "978-0141439513",
            cover:'https://cdn.kobo.com/book-images/08ba5a67-f48d-420e-be8e-6de7a73b7d85/1200/1200/False/pride-prejudice-13.jpg'
            },
            {title: "The Catcher in the Rye",
            author: "J.D. Salinger",
            year: 1951,
            genre: "Coming-of-age Fiction",
            pages: 214,
            publisher: "Little, Brown and Company",
            isbn: "978-0316769488",
            cover:'https://cdn.britannica.com/94/181394-050-2F76F7EE/Reproduction-cover-edition-The-Catcher-in-the.jpg'
            }]}
   }
}
</script>
<style v-if="true">
  body {
    background-image: url('https://images.unsplash.com/photo-1718743256288-e77382a88aaf?q=80&w=1887&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
    background-size: contain;
  }
</style>
<style scoped>
/* div#app{
   background-color: black;
 */
 
section{
    /* display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center; */
    display: grid;
    grid-template-columns: repeat(auto-fit, minMax(200px, 1fr))
}
.myCard {
    background: rgba( 0, 0, 0, 0.25 );
box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
backdrop-filter: blur( 6px );
-webkit-backdrop-filter: blur( 6px );
border-radius: 10px;
border: 1px solid rgba( 255, 255, 255, 0.18 );
    margin: 1em;
    border-radius: 1em;
    display: grid;
}
.myCard:hover{
    background: rgba(255, 255, 255, 0.116);
    box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    backdrop-filter: blur( 4px );
    -webkit-backdrop-filter: blur( 4px );
    border-radius: 10px;
    border: 1px solid rgba( 255, 255, 255, 0.18 );
}
.myCard:hover .moreInfo>*{
    text-shadow: 2px 2px 2px rgba(0, 0, 0, 0.541);
}
.myCoverStyle img{
    width: 8em;
    padding: em;
}
.moreInfo{
    display: flex;
    flex-direction: column;
    text-align: left;
    padding: 2em;
}
.moreInfo>*{
    padding: 0;
    margin: 0;
    color: white;
}
</style>
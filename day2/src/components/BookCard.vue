<template>
 
  <div class="container-lg p-4" >
    <div class="card" style="width: 18rem" >
      <img :src="book.imageLink" class="card-img-top" alt="book cover" />
      <div class="card-body">
        <h5 class="card-title">{{book.title}}</h5>
      </div>
      <ul class="list-group list-group-flush">
        <li class="list-group-item"><b>Author : </b> {{book.author}}</li>
        <li
          :class="[book.pages < 300 ? 'less' : 'more', 'list-group-item']"
        >
          <b>No. Pages :</b> {{book.pages}}
        </li>
        <li class="list-group-item">
          <b>Price : </b> {{formatPrice(Math.round(Math.random() * 1000))}}
        </li>
      </ul>
      <div class="card-body">
        <a
          class="card-link"
          @click="addToWishlist(book)"
          
          > Add to WishList</a
        >
         
      </div>
    </div>
  </div>
  
</template>

<script>
export default {
  props: ["book","isBookInWishList", "addToWishlist", "formatPrice"]
};
</script>

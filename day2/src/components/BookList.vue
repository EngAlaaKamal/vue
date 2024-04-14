<template>
  <div>
    <div class="row justify-content-center" >
      <div class="col-md-4 mb-4" v-for="book in books" :key="book.id">
        <BookCard
          :book="book"
          :addToWishlist="addToWishlist"
          :formatPrice="formatPrice"
          :isBookInWishList="isBookInWishList"
        />
      </div>
    </div>
  </div>

  
</template>

<script>
import BookCard from "./BookCard.vue";

export default {
  components: {
    BookCard,
  },
  props: ["books","isBookInWishList", "addToWishlist", "formatPrice"],
};
</script>

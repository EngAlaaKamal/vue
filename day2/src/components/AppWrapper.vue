<template>
  <div class="container mt-5">
    <NavBar  @toggleWishlist="toggleWishlist" />
    <BookList
      v-if="!isWishListVisible"
      :books="books"
      :addToWishlist="addToWishlist"
      :formatPrice="formatPrice"
      :isBookInWishList="isBookInWishList"
    />
    <WishList
      v-if="isWishListVisible"
      :booksWished="booksWished"
      :formatPrice="formatPrice"
      :removeFromWishlist="removeFromWishlist"
    />
  </div>
</template>

<script>
import NavBar from "./NavBar.vue";
import BookList from "./BookList.vue";
import WishList from "./WishList.vue";
import { books } from "../../booksData";  

export default {
  components: {
    NavBar,
    BookList,
    WishList,
  },
  data() {
    return {
      books: books,  
      booksWished: new Set([]),
      isWishListVisible: false,
    };
  },
  methods: {
    addToWishlist(book) {
      this.booksWished.add(book);
    },
    removeFromWishlist(book) {
      this.booksWished.delete(book);
    },
    isBookInWishList(book) {
      return this.booksWished.has(book);
    },
    formatPrice(price) {
      return Intl.NumberFormat("ar-SA", {
        style: "currency",
        currency: "SAR",
      }).format(price);
    },
    toggleWishlist() {
      this.isWishListVisible = !this.isWishListVisible;
    },
  },
};
</script>

<style>
.container-lg {
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  justify-content: space-around;
}
a {
  cursor: pointer;
}
.more {
  color: green;
  font-weight: 600;
}
.less {
  color: red;
  font-weight: 600;
}
</style>

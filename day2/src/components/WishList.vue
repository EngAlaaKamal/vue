<template>
  <div class="container-lg" id="wish-list">
    <h1 v-if="booksWished.size <= 0">Empty wish list</h1>
    <table class="table" v-else>
      <thead>
        <tr>
          <th scope="col">ID</th>
          <th scope="col">Title</th>
          <th scope="col">Author</th>
          <th scope="col">Category</th>
          <th scope="col">Price</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="book in booksWished" :key="book.id">
          <td>{{book.id}}</td>
          <td>{{book.title}}</td>
          <td>{{book.author}}</td>
          <td>{{book.category}}</td>
          <td>{{book.price}}</td>
          <td><a @click="removeFromWishlist(book)">Remove</a></td>
        </tr>
      </tbody>
    </table>
  </div>
   
</template>

<script>
export default {
  props: ["booksWished", "formatPrice", "removeFromWishlist"],
};
</script>

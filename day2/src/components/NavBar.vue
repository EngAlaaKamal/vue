<template>
  <nav class="navbar navbar-expand-lg" style="background-color: #e2d8f3;">
        <div class="container-fluid">
          <a class="navbar-brand" @click.prevent="$emit('toggleWishlist')">BOOKS</a>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarNav"
            aria-controls="navbarNav"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
              <li class="nav-item">
                <a
                  class="nav-link active"
                  aria-current="page"
                  @click.prevent="$emit('toggleWishlist')"
                  >Wishlist</a
                >
              </li>
            </ul>
          </div>
        </div>
      </nav>
</template>

<script>
export default {
  emits: ["toggleWishlist"],
};
</script>
 
<template>
  <div class="col-3 col-xl-3 book-info mt-5">
    <div class="container-img">
      <img src="@/assets/book.svg" alt="book-item">
    </div>
    <h1 class="book-title">
      Book title
    </h1>
    <div class="author-name">
      Author name
    </div>
    <div class="book-field">
      Book field
    </div>
    <button type="submit" @click.prevent="setOption($event)">
      <svg
        id="Layer_1"
        version="1.1"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        x="0px"
        y="0px"
        width="44px"
        height="44px"
        viewBox="0 0 64 64"
        enable-background="new 0 0 64 64"
        xml:space="preserve"
      >
        <path
          fill="none"
          stroke="#000000"
          stroke-width="2"
          stroke-miterlimit="10"
          d="M1,21c0,20,31,38,31,38s31-18,31-38c0-8.285-6-16-15-16c-8.285,0-16,5.715-16,14c0-8.285-7.715-14-16-14C7,5,1,12.715,1,21z"
        />
      </svg>
    </button>
  </div>
</template>

<script>
export default {
  name: 'Book',
  props: {
    bookIndex: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      id: 0,
      liked: false
    }
  },
  methods: {
    setOption (event) {
      const heart = event.target.firstElementChild

      if (!this.liked) {
        this.setLike(heart)
      } else {
        this.setUnlike(heart)
      }
    },
    setLike (element) {
      try {
        element.removeAttribute('fill')
        element.setAttribute('fill', 'red')
        this.liked = true
      } catch (error) {
        console.log(error)
      }
    },
    setUnlike (element) {
      try {
        // element.removeAttribute('fill')
        element.fill = '#000000'
        this.liked = false
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>

<style scoped>
    .book-info {
        padding: 0 20px; text-align: center;
    }
    .book-info button {
        position: absolute;
        bottom: 70px;
        right: 70px;
        border: 0;
        background-color: unset;
    }
    .container-img img {
        width: 215px;
    }
    .book-title, .author-name, .book-field {
        text-align: left;
    }
</style>

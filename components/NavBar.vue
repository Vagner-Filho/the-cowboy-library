<template>
  <div class="navbar navbar-light">
    <div class="container-fluid">
      <h1 class="text-initial">
        Livraria do cowboy
      </h1>
      <div class="text-end dl-modes">
        <button v-if="!darkMode" type="button" @click="darkMode = !darkMode">
          Dark Mode
        </button>
        <button v-else type="button" @click="darkMode = !darkMode">
          Light Mode
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      darkMode: false
    }
  }
}
</script>

<style scoped>
    .dl-modes button {
        background-color: unset;
        border: 0;
        font-size: 2rem;
    }
    .navbar {
        background-color: #95d9da;
    }
    h1, button {
        color: white;
    }
</style>

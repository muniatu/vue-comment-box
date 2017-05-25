<template>
  <div class="comment-list" id="comment-section">
    <div class="comment-list-header">
        <h1 class="user">Adrià Compte</h1>
        <div class="user-status"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'comment-list',
  data() {
    return {
      loading: false,
      data: {}
    }
  }
}
</script>

<style>
#comment-section{
  position:relative;
  padding: 2rem;
  background-color:white;
}
</style>
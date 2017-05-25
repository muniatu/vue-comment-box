<template>
  <div id="app">
    <nav class="nav clearfix">
      <div class="container">
        <ul class="nav-list nav-left">
          <li class="active">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
              <use xlink:href="#user-icon"></use>
            </svg>
          </li>
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
              <use xlink:href="#menu-icon"></use>
            </svg>
          </li>
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
              <use xlink:href="#search-icon"></use>
            </svg>
          </li>
        </ul>
        <ul class="nav-list nav-right">
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="#ffffff">
              <use xlink:href="#calendar-icon"></use>
            </svg>
          </li>
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
              <use xlink:href="#mail-icon"></use>
            </svg>
          </li>
          <li>
            <img class="message-profile-pic" src="https://api.adorable.io/avatars/2" width="24px">
          </li>
        </ul>
      </div>
    </nav>
  
    <section>
      <div class="container">
        <comment-list></comment-list>
      </div>
    </section>
  </div>
</template>

<script>
import CommentList from './CommentList.vue'

export default {
  name: 'app',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
      CommentList 
  }
}
</script>
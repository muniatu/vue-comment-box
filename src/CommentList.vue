<template>
  <section class="comment-list" id="comment-section">
    <div class="comment-list-header">
      <h1 class="user">Adrià Compte</h1>
      <div class="user-status">
        <span>
          <svg height="8" width="8">
            <circle cx="4" cy="4" r="4" stroke="none" stroke-width="0" fill="#69c733" />
          </svg>
        </span>
        <span>ONLINE</span>
      </div>
    </div>
    <div class="comment-list-body">
      <div v-for="comments in comments" class="comment-list-comment">
        <div class="comment-list-comment-avatar">
          <img :src="comments.avatar" width="40" />
        </div>
        <div class="comment-list-comment-content">
          <h4 class="comment-list-comment-content-user">
            {{comments.author}}
          </h4>
          <p class="comment-list-comment-content-text">
            {{comments.content}}
          </p>
        </div>
  
      </div>
    </div>
    <div class="comment-list-footer">
      <textarea type="text" v-model="msg" @keyup.enter="addCommentKey" placeholder="Start typing your message or drop file..."></textarea>
      <button id="send-button" @click="addComment" >SEND</button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'comment-list',
  data: function () {
    return {
      user: 'Adrià Compte',
      userAvatar: 'https://api.adorable.io/avatars/2',
      msg: '',
      comments: [
        { avatar: 'https://api.adorable.io/avatars/8', author: 'Alex Mortinger', content: 'Lorem ipsum dolor sit amet, qui ea prodesset similique, ea mea nostrum hendrerit definitionem. Graeco commodo scripta mei ad, et nibh adolescens suscipiantur sea, ex diceret facilisis incorrupte duo.' },
        { avatar: 'https://api.adorable.io/avatars/10', author: 'John Doe', content: 'Eos choro quidam intellegat ne, voluptua molestiae usu et, ad fuisset officiis his. Veri nominavi vis cu, mollis vocent partiendo est in. Usu reprimique appellantur ne, aliquip dissentiet qui cu, id feugiat omnesque torquatos ius. Mei et nonumy adolescens.' },
        { avatar: 'https://api.adorable.io/avatars/24', author: 'Ada Lovelace', content: 'Sit an mazim democritum, modo vituperatoribus sed te. Mea ei accumsan petentium. An legendos scriptorem mei. Duis accusam definitiones ius at, oporteat inimicus cu vel, magna vitae erroribus sit id. No dico efficiendi vix, ex altera theophrastus sed, vis facer corrumpit no.' }
      ]
    }

  },

  methods: {
    addComment: function () {
      this.comments.push({
        avatar: this.userAvatar,
        author: this.user,
        content: this.msg
      })
      this.msg = ''
    },
    //allows user to add line break
    addCommentKey: function (event) {
    	if (!event.shiftKey) {
      	this.addComment()
      }
    }
  }
}
</script>

<style>
.comment-list-header {
  background-color: #f1f1f1;
  height: 5rem;
}

.user {
  padding: 1.7rem 1rem 1.7rem 3rem;
  float: left;
}

.user-status {
  float: left;
  padding: 1.8rem 0;
}

.user-status span {
  font-size: 12px;
  color: #aaa;
}

#comment-section {
  position: relative;
  background-color: white;
}

.comment-list-body {
  padding: 2rem 3rem 3rem 3rem;
}
.comment-list-comment{
  position:relative;
}

.comment-list-comment .author {
  margin-bottom: 0.5rem;
}

.comment-list-comment-avatar {
  position:absolute;
  padding: 2rem 0;
}
.comment-list-comment:first-child .comment-list-comment-avatar{
  padding-top: 0;
}

.comment-list-comment-content {
  padding: 2rem 0 2rem;
  margin-left: 4.5rem;
  border-top: 1px solid #eee;
  vertical-align: top;
  word-wrap:break-word;
}
.comment-list-comment:first-child .comment-list-comment-content{
  border: none;
  padding-top: 0;
}

.comment-list-comment-avatar img {
  border-radius: 50%;
}

.comment-list-footer {
  background-color: #f1f1f1;
  height: 6rem;
}

.comment-list-footer textarea {
  background: transparent;
  border: none;
  padding: 2.5rem 3rem 1.2rem;
  resize: none;
  width: 60%;
}

.comment-list-footer textarea:focus {
  outline: none;
}

#send-button {
  background-color: #1b8ad2;
  color: white;
  padding: 1rem 3rem;
  border-radius: 2px;
  border: none;
  float: right;
  margin: 1.5rem 3rem;
}
</style>
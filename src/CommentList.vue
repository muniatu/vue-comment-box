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
        <h4 class="author">
          {{comments.author}}
        </h4>
        <p v-html="comments.content" class="comment-list-comment-content"></p>
  
      </div>
    </div>
    <div class="comment-list-footer">
      <textarea type="text" v-model="msg" placeholder="Start typing your message or drop file..."></textarea>
      <button id="send-button" @click="addComment">SEND</button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'comment-list',
  data: function () {
    return {
      user: 'Adrià Compte',
      comments: [
        { author: 'Alex Mortinger', content: 'Lorem ipsum dolor sit amet, qui ea prodesset similique, ea mea nostrum hendrerit definitionem. Graeco commodo scripta mei ad, et nibh adolescens suscipiantur sea, ex diceret facilisis incorrupte duo.' },
        { author: 'John Doe', content: 'Eos choro quidam intellegat ne, voluptua molestiae usu et, ad fuisset officiis his. Veri nominavi vis cu, mollis vocent partiendo est in. Usu reprimique appellantur ne, aliquip dissentiet qui cu, id feugiat omnesque torquatos ius. Mei et nonumy adolescens.' },
        { author: 'Ada Lovelace', content: 'Sit an mazim democritum, modo vituperatoribus sed te. Mea ei accumsan petentium. An legendos scriptorem mei. Duis accusam definitiones ius at, oporteat inimicus cu vel, magna vitae erroribus sit id. No dico efficiendi vix, ex altera theophrastus sed, vis facer corrumpit no.' }
      ]
    }

  },

  methods: {
    addComment: function () {
      this.comments.push({
        author: this.user,
        content: this.msg
      })
      this.msg = '';
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
.user-status{
  float:left;
  padding: 1.8rem 0;
}
.user-status span{
  font-size: 12px;
  color:#aaa;
}
#comment-section {
  position: relative;
  background-color: white;
}

.comment-list-body {
  padding: 0 3rem;
}

.comment-list-comment {
  border-top: 1px solid #eee;
  padding: 2rem 0;
  word-wrap: break-word;
}

.comment-list-comment:first-child {
  border: none;
}
.comment-list-comment:last-child {
  padding-bottom: 3rem;
}
.comment-list-comment .author{
  margin-bottom:0.5rem;
}
.comment-list-footer {
  background-color: #f1f1f1;
  height: 6rem;
}

.comment-list-footer textarea {
  background: transparent;
  border: none;
  padding: 2.5rem 3rem 1.5rem;
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
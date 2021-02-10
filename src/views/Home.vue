<template>
  <div id="home">
    <div class="add-post">
      <input type="text" placeholder="add a post" v-model="post_content">
      <img src="@/assets/add_post_btn.png" alt="" class="post-btn" @click="addPost">
    </div>
    <PostItem v-for="post in posts" :key="post.nb_likes" :postInfos="post" :username="username"/>
  </div>
</template>

<script>
import PostItem from '@/components/PostItem.vue';
const DateModule = require('@/modules/date.js')
export default {
  name: 'Home',
  components: {
    PostItem,
  },
  props: {
    username: {
      type: String,
      default:''
    },
  },
  data() {
    return {
      post_content: '',
      posts: [
        {
          date: '10/02/2021',
          nb_likes: 12,
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. trop bien ce workshop Ut laoreet fringilla lorem, sit amet semper neque interdum quis'
        },
        {
          date: '25/12/2020',
          nb_likes: 4,
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.Joyeux noël les potes . Ut laoreet fringilla lorem, sit amet semper neque interdum quis'
        },
        {
          date: '28/03/2020',
          nb_likes: 62,
          content: 'eros nisl, eu ultrices massa nulla ac augue Donec id efficitur nulla, eu efficitur tellus. In ut sagittis urna, non tempus felis. Fusce convallis, ligula a mattis suscipit'
        },
        {
          date: '19/07/2019',
          nb_likes: 44,
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. trop bien ce workshop Ut laoreet fringilla lorem, sit amet semper neque interdum quis'
        }
      ]
    }
  },
  methods: {
    addPost() {
      let new_post = {
        date: DateModule.getCurrentDate(),
        nb_likes: 0,
        content:   this.post_content,
      }
      this.posts.push(new_post);
    }
  },
}
</script>

<style lang="scss" scoped>
* {
  margin: auto;
  margin-top: 20px;
}
.add-post {
  display: flex;
  width: 800px;
  height: 75px;
  align-content: center;
  input {
    border: 1px solid grey;
  }
  img {
    cursor: pointer;
  }
}
h2 {
  color: #45AAF2;
  font-family: 'Lobster', cursive;
  font-size: 1.7em;
}
</style>
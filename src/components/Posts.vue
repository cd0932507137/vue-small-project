<template>
  <div class="container pt-4">
    <table class="table table-striped">
      <thead>
        <tr>
          <th scope="col">id</th>
          <th scope="col">title</th>
          <th scope="col">body</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="post in posts" :key="post.id">
          <th scope="row">{{post.id}}</th>
          <td>{{post.title}}</td>
          <td>{{post.body}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'PostsExample',
  data () {
    return {
      posts: []
    }
  },
  created () {
    axios.get('https://jsonplaceholder.typicode.com/posts').then(res => {
      this.posts = res.data
      console.log(this.posts)
    })
  }
}
</script>
<style>
</style>

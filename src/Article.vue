<template>
  <div class="article">
    <h1>{{ title }}</h1>

    <p>Published on {{ published | moment }}</p>
    <p class="lead">{{ content }}</p>
    <app-author></app-author>
  </div>
</template>

<script>
  // import moment from 'moment';
  import Author from './Author.vue';

  export default {
    data() {
      return {
        title: "Vue.js is awesome and powerful",
        published: new Date(),
        content: "Vue.js' power is only limited by its awesomeness."
      };
    },
    filters: {
      moment: function(value) {
        return moment(value).format('MMMM Do');
      }
    },
    components: {
      'app-author': Author
    }
  }
</script>

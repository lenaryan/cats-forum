<template>
  <div id="app">
    <MessageList 
      v-bind:messages="messages"
    />
  </div>
</template>

<script>
import MessageList from '@/components/MessageList'
export default {
  name: 'app',
  data() {
    return {
      messages: [
        {id: 1, user: 'Leanne Graham', title: 'lorem ipsum', body: 'lorem lorem ipsum ipsum'},
        {id: 2, user: 'Leanne Graham', title: 'lorem', body: 'lorem lorem ipsum lorem ipsum ipsum'},
        {id: 3, user: 'Leanne Graham', title: 'ipsum', body: 'lorem lorem ipsum lorem ipsum ipsum'}
      ]
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/posts?_limit=7')
    .then(response => response.json())
    .then(json => this.messages = json)
  },
  components: {
    MessageList
  }
}
</script>
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
        {id: 1, name: 'Leanne Graham', title: 'lorem ipsum', body: 'lorem lorem ipsum ipsum'},
        {id: 2, name: 'Leanne Graham', title: 'lorem', body: 'lorem lorem ipsum lorem ipsum ipsum'},
        {id: 3, name: 'Leanne Graham', title: 'ipsum', body: 'lorem lorem ipsum lorem ipsum ipsum'}
      ],
      users: []
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/users')
    .then(response => response.json())
    .then(json => this.users = json);

    fetch('https://jsonplaceholder.typicode.com/posts')
    .then(response => response.json())
    .then(json => {
      this.messages = json;
      this.messages.forEach(mess => {
        this.users.forEach(user => {
          if (mess.userId == user.id) {
            mess.name = user.name;
          };
        })
      });
    });
  },
  components: {
    MessageList
  }
}
</script>
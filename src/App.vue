<template>
  <div id="app">
    <MessageList 
      v-bind:messages="filteredMessages"
    />
    <div class="filter">
      <p class="filter__title">Фильтры</p>
      <label class="filter__label">Имя/Название
          <input type="text" class="filter__input" v-model="filter1">
      </label>
      <label class="filter__label">Контент
          <input type="text" class="filter__input" v-model="filter2">
      </label>
    </div>
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
      users: [],
      filter1: '',
      filter2: ''
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/users')
    .then(response => response.json())
    .then(json => this.users = json);

    fetch('https://jsonplaceholder.typicode.com/posts?_limit=7')
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
  computed: {
    filteredMessages() {
      if (this.filter1 == '' && this.filter2 == '') {
        return this.messages;
      }
      
      if (this.filter1 != '' && this.filter2 == '') {
        return this.messages.filter(mes => mes.title.startsWith(this.filter1));
      }

      if (this.filter1 == '' && this.filter2 != '') {
        return this.messages.filter(mes => mes.body.startsWith(this.filter2));
      }

      if (this.filter1 != '' && this.filter2 != '') {
        return this.messages.filter(mes => mes.title.startsWith(this.filter1) && mes.body.startsWith(this.filter2));
      }
    }
  },
  components: {
    MessageList
  }
}
</script>
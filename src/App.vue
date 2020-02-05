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
        {id: 1, pic: 'http://placekitten.com/100/100', name: 'Leanne Graham', title: 'lorem ipsum', content: 'lorem lorem ipsum ipsum'},
        {id: 2, pic: 'http://placekitten.com/100/100', name: 'Leanne Graham', title: 'lorem', content: 'lorem lorem ipsum lorem ipsum ipsum'},
        {id: 3, pic: 'http://placekitten.com/100/100', name: 'Leanne Graham', title: 'ipsum', content: 'lorem lorem ipsum lorem ipsum ipsum'}
      ]
    }
  },
  components: {
    MessageList
  }
}
</script>
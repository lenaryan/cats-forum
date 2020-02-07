<template>
    <div class="message-list">
        <Message 
            v-for="mes in messages"
            v-bind:mes="mes"
        />
    </div>
</template>

<script>
import Message from '@/components/Message'
export default {
    props: [
        'messages'
    ],
    components: {
        Message
    }
}
</script>

<style>
    .message-list {
        width: 75%;
    }
</style>
<template>
    <div>
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
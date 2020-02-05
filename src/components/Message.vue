<template>
    <section class="message">
        <img src="http://placekitten.com/100/100" alt="" class="message__pic">
        <div class="message__text">
            <p class="message__name">{{mes.name}}</p>
            <p class="message__title">{{mes.title}}</p>
            <p class="message__content">{{mes.content}}</p>
        </div>
    </section>
</template>

<script>
export default {
    props: [
        'mes'
    ]
}
</script>
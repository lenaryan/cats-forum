<template>
    <section class="message">
        <img src="http://placekitten.com/100/100" alt="" class="message__pic">
        <div class="message__text">
            <p class="message__name">{{mes.name}}</p>
            <p class="message__title">{{mes.title}}</p>
            <p class="message__content">{{mes.body}}</p>
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

<style scoped>
    .message {
        background: #E6F5FF;
        border: 1px solid #c1dff3;
        padding: 15px 25px;
        margin-bottom: 15px;
    }

    .message__pic {
        float: left;
        margin-right: 15px;
    }

    .message__name {
        color: #939291;
        font-size: 15px;
        margin: 5px 0 10px;
    }

    .message__title {
        font-size: 23px;
        margin: 0 0 5px;
    }

    .message__content {
        font-size: 19px;
        margin: 0;
    }

    @media (max-width: 480px) {
        .message__content {
            clear: both;
        }

        .message__pic {
            margin-bottom: 10px;
        }
    }
</style>
<template>
    <div class = "post">
        <div><strong><h3>{{post_title}}</h3></strong></div>
        <div><strong>Описание: </strong>{{post_body}}</div>
    </div>
</template>

<script>
export default {
    props: {
        post_title: {
            type: String,
            required: true, //Обязательность данного пропса
        },
        post_body: {
            type: String,
            required: true,
        }
    }
}
</script>

<style>
.post {
    padding: 15px;
    border: 2px solid #002c85;
    margin-top: 10px;
}
</style>
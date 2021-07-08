<template>
    <div class = "post">
        <post-tags :tags="tags" :post_tags="post_tags"/>
        <div><strong><h3>{{post_title}}</h3></strong></div>
        <div class='post_body'><strong>Описание: </strong>{{post_body}}</div>
        <div class="vault">
            <h4>{{post_author}}</h4>
            <h4>{{post_date}}</h4>
        </div>
    </div>
</template>

<script>
import PostTags from './PostTags.vue';
export default {
    components: {
        PostTags
    },

    props: {
        post_title: {
            type: String,
            required: true, //Обязательность данного пропса
        },
        post_body: {
            type: String,
            required: true,
        },
        post_author: {
            type: String,
            required: true,
        },
        post_date: {
            type: String,
            required: true,
        },
        tags: {
            type: Array,
            required: true,
        },
        post_tags: {
            type: Array,
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

.vault {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-top: 10px;
    color: grey;
}

.post_body {
    margin-top: 10px;
}
</style>
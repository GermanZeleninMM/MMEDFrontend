<template>
    <div class = "post">
        <div>
            <div class="post_footer">
                <div>
                    <post-tags :tags="tags" :post_tags="post.tags"/>
                    <div><strong><h3>{{post.title}}</h3></strong></div>
                </div>
                <div>
                    <my-button style="margin-right: 0px" @click="$emit('remove', post)">Удалить</my-button>
                </div>
            </div>
            <div class='post_body'>
                <strong>Описание: </strong>{{post.body_post}}
            </div>
            <div class="vault">
                <h4>{{post.author}}</h4>
                <h4>{{post.public_date}}</h4>
            </div>
        </div>
    </div>
</template>

<script>
import PostTags from './PostTags.vue';
import MyButton from './UI/MyButton.vue';
export default {
    components: {
        PostTags, MyButton
    },

    props: {
        tags: {
            type: Array,
            required: true,
        },
        post: {
            type: Object,
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

.post_footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>
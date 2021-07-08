<template>
    <div><h3>Последние новости</h3></div>
    <post-item :post_title="post.title" :post_author="post.author" :post_date="post.public_date" :post_body="post.body_post" :tags="tags" v-for="post in posts" v-bind:key="post.id" :post_tags="post.tags"/>
</template>

<script>
import PostItem from './PostItem.vue';

export default {
  components: { PostItem },
    component: {
        PostItem
    },

    props: {
        posts: {
            type: Array,
            required: true, //Обязательность данного пропса
        },
        tags: {
            type: Array,
            required: true,
        }
    }
}
</script>

<style>

</style>
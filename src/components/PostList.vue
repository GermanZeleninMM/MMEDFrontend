<template>
    <div><h3>Последние новости</h3></div>
    <post-item :post_title="post.title" :post_body="post.body_post" v-for="post in posts" v-bind:key="post.id"/>
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
        }
    }
}
</script>

<style>

</style>
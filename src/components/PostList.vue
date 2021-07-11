<template>
    <div v-show="posts.length > 0">
        <div><h3>Последние новости</h3></div>
        <post-item :tags="tags" v-for="post in posts" v-bind:key="post.id" :post="post" @remove="$emit('remove', post)"/>
    </div>
    <div v-show="posts.length == 0">
        <h1 style="color: red">Новостей пока нет. Станьте первым!</h1>
    </div>
</template>


<script>
import PostItem from './PostItem.vue';
import MyButton from './UI/MyButton.vue';

export default {
  components: { PostItem, MyButton },
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
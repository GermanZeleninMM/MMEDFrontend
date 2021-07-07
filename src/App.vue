<template>
    <div class="app">
        <post-form @createpost = "createPost"/>
        <post-list v-bind:posts="posts"/> 
    </div>
</template>

<script>
    import PostForm from './components/PostForm.vue'
    import PostList from './components/PostList.vue'
    export default {
        components: {
            PostForm, PostList
        },

        data() {
            return {
                posts: [
                    {id: 1, title: 'Message 1', body_post: 'MechMath'},
                    {id: 2, title: 'Привет! Это начало нового проекта', body_post: '7 июля - начало разработки данного проекта'},
                    {id: 3, title: 'Message 3', body_post: 'MechMath MSU'},
                    {id: 4, title: 'Message 4', body_post: ''},
                ]
            }
        },

        methods: {
            createPost(post){
                this.posts.push(post);
            }
        }
    }
</script>

<style>
* {
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
}

.app {
    padding: 20px;
}
</style>

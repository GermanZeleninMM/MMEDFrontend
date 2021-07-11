<template>
    <div class="app">
        <post-form @createpost = "createPost" :tags="tags"/>
        <post-list v-bind:posts="posts" :tags="tags" @remove="removePost"/> 
    </div>
</template>

<script>
    import PostForm from './components/PostForm.vue'
    import PostList from './components/PostList.vue'
import MyButton from './components/UI/MyButton.vue'
    export default {
        components: {
            PostForm, PostList,
                MyButton
        },

        data() {
            return {
                posts: [
                    {
                        id: 1, 
                        title: 'В Японии ввели режим ЧС за две недели до начала Олимпиады', 
                        body_post: 'Премьер-министр Японии Есихидэ Суга объявил о введении в стране режима чрезвычайной ситуации', 
                        author: 'Герман Зеленин', 
                        public_date: '7 Июля 2021 года',
                        tags: [1, 2, 3]
                    },
                    {
                        id: 2, 
                        title: 'Объяснено стремление США к постоянному доминированию', 
                        body_post: 'Научный руководитель Центра республиканских исследований Родион Белькович объяснил причины стремления США к постоянному доминированию на мировой арене. ', 
                        author: 'admin', 
                        public_date: '8 Июля 2021 года',
                        tags: [2, 3]
                    },
                    {
                        id: 3, 
                        title: 'Мэр Лобни ушел в отставку', 
                        body_post: 'Глава подмосковной Лобни Евгений Смышляев, который стал фигурантом уголовного дела о злоупотреблении полномочиями, уходит в отставку по собственному желанию.', 
                        author: 'admin', 
                        public_date: '9 Июля 2021 года',
                        tags: [1]
                    },
                    {
                        id: 4, 
                        title: 'Власти продлили посещение летних веранд в Москве без QR-кодов', 
                        body_post: 'Власти Москвы продлили посещение летних веранд без QR-кодов до 1 августа. Об этом сообщается на официальном сайте мэра столицы Сергея Собянина.', 
                        author: 'admin', 
                        public_date: '9 Июля 2021 года',
                        tags: [1, 3]
                    },
                ],

                tags: [
                    {
                        id: 1,
                        title: 'В России',
                    },
                    {
                        id: 2,
                        title: 'В мире',
                    },
                    {
                        id: 3,
                        title: 'Важное',
                    },
                    {
                        id: 4,
                        title: 'Политика',
                    },
                    {
                        id: 5,
                        title: 'Экономика',
                    },
                    {
                        id: 6,
                        title: 'Общество',
                    },
                    {
                        id: 7,
                        title: 'Происшествия',
                    },
                    {
                        id: 8,
                        title: 'Наука',
                    },
                ]
            }
        },

        methods: {
            createPost(post){
                this.posts.push(post);
            },
            removePost(post) {
                this.posts = this.posts.filter(p => p.id !== post.id);
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

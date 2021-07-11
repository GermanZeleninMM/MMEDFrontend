<template>
    <form @submit.prevent>
        <h3>Создание поста</h3>
        <my-input type="text" placeholder="Заголовок новости" v-model="post.title"/> <!-- v-bind это связывание значения в инпуте и дате -->
        <my-input type="text" placeholder="Описание" v-model="post.body_post"/> <!-- Можно проще, v-model="post.title" - двустороннее связывание-->
        <form-checkbox :tags="tags" @sendTags="input_tags" nameofformcheckbox="Категории"/>
        <my-button @click="createPost">Создать</my-button> <!--Слушатель нажатия @click -->
    </form>
</template>

<script>
import FormCheckbox from './FormCheckbox.vue';
import MyButton from './UI/MyButton.vue';
export default {
    components: {
        FormCheckbox, MyButton
    },

    data () {
        return {
            post: {
                id: '',
                title: '',
                body_post: '',
                author: 'admin',
                public_date: '08.07.2021',
                tags: [],
            },
        }
    },

    methods: {
        createPost () {
            const monthNames = ["Января", "Февраля", "Марта", "Апреля", "Мая", "Июня", "Июля", "Августа", "Сентября", "Октября", "Ноября", "Декабря"];
            const dateObj = new Date();
            const month = monthNames[dateObj.getMonth()];
            const day = String(dateObj.getDate()).padStart(2, '0');
            const year = dateObj.getFullYear();
            this.post.public_date = day + ' '+ month  + ' ' + year + ' года';

            this.post.id = Date.now();
            this.$emit('createpost', this.post);
            this.post = {
                title: '',
                body_post: '',
                author: 'admin',
                public_date: '',
                tags: []
            }
        },

        input_tags (cTags) {
            this.post.tags = cTags;
        }
    },

    props: {
        tags: {
            type: Array,
            required: true,
        }
    }
}
</script>

<style>
form {
    display: flex;
    flex-direction: column;
}

.input_form {
    width: 100%;
    border: 2px solid #002c85;
    padding: 10px 15px;
    margin-top: 15px;
}
</style>
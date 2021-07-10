<template>
    <form @submit.prevent>
        <h3>Создание поста</h3>
        <input class="input_form" type="text" placeholder="Заголовок новости" v-bind:value="post.title" @input="post.title = $event.target.value"> <!-- v-bind это связывание значения в инпуте и дате -->
        <input class="input_form" type="text" placeholder="Описание" v-model="post.body_post"> <!-- Можно проще, v-model="post.title" - двустороннее связывание-->
        <form-checkbox :tags="tags" @sendTags="input_tags"/>
        <button class="button_form" @click="createPost">Создать</button> <!--Слушатель нажатия @click -->
    </form>
</template>

<script>
import FormCheckbox from './FormCheckbox.vue';
export default {
    components: {
        FormCheckbox
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
            }
        }
    },

    methods: {
        createPost () {
            this.post.id = Date.now();
            this.$emit('createpost', this.post);
            this.post = {
                title: '',
                body_post: '',
                author: 'admin',
                public_date: '08.07.2021',
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

.button_form {
    align-self: flex-end;
    margin: 15px;
    padding: 10px 15px;
    background: none;
    color: #002c85;
    border: 2px solid #002c85;
}

.input_form {
    width: 100%;
    border: 2px solid #002c85;
    padding: 10px 15px;
    margin-top: 15px;
}
</style>
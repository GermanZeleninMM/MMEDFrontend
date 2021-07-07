<template>
    <form @submit.prevent>
        <h3>Создание поста</h3>
        <input class="input_form" type="text" placeholder="Заголовок новости" v-bind:value="post.title" @input="post.title = $event.target.value"> <!-- v-bind это связывание значения в инпуте и дате -->
        <input class="input_form" type="text" placeholder="Описание" v-model="post.body_post"> <!-- Можно проще, v-model="post.title" - двустороннее связывание-->
        <button class="button_form" @click="createPost">Создать</button> <!--Слушатель нажатия @click -->
    </form>
</template>

<script>
export default {
    data () {
        return {
            post: {
                id: '',
                title: '',
                body_post: '',
            }
        }
    },

    methods: {
        createPost () {
            this.post.id = Date.now();
            this.$emit('createpost', this.post);
            this.post = {
                title: '',
                body_post: ''
            }
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
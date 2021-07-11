<template>
    <div class="footer_checkbox">
        <h4>{{nameofformcheckbox}}</h4>
    </div>
    <div class="formcheckbox">
        <div v-for="tag in tags" v-bind:key="tag.id">
            <input type="checkbox" v-bind:value="tag.id" v-model="cTags" @change="sendTags" class="input_checkbox">
            <label for="">{{tag.title}}</label>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            cTags: []
        }
    },

    props: {
        tags: {
            type: Array,
            required: true,
        },
        nameofformcheckbox: {
            type: String,
            required: true,
        }
    },

    methods: {
        sendTags () {
            this.$emit('sendTags', this.cTags);
        }
    }
}
</script>

<style>
@media (min-width: 450px) {
    .formcheckbox {
        display: grid;
        grid-template-columns: repeat(5, 1fr);
        grid-template-rows: repeat(5, auto);
        padding: 10px 15px;
    }
}
@media (min-width: 450px) {
    .formcheckbox {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(3, auto);
        padding: 10px 15px;
    }
}

.input_checkbox {
    margin-right: 10px;
    margin-top: 10px;
}

.footer_checkbox {
    margin-top: 12px;
}
</style>
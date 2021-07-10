<template>
    <div class="formcheckbox">
        <div v-for="tag in tags" v-bind:key="tag.id">
            <input type="checkbox" v-bind:value="tag.id" v-model="cTags" @change="sendTags">
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

.formcheckbox {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: 10px 15px;
    margin-top: 15px;
}
</style>
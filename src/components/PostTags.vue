<template>
    <div class="post_top">
        <div v-for="tag in tags" v-bind:key="tag.id">
            <div v-if="post_tags.indexOf(tag.id) != -1">
                <div class="post_tags">
                    <h5>{{tag.title}}</h5>
                </div>
            </div>
        </div>
    </div>    
</template>

<script>
export default {
    props: {
        tags: {
            type: Array,
            required: true,
        },
        post_tags: {
            type: Array,
            required: true,
        }
    }
}
</script>

<style>
.post_top {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
}

.post_tags {
    border: 2px solid #002c85;
    border-radius: 5px;
    margin-right: 5px;
    margin-bottom: 5px;
    color: #002c85;
    padding: 2px;
    text-align: center;
    display: flex;
    align-items: center
}
</style>
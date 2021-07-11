<template>
    <button class="button_form">
        <slot>

        </slot>
    </button>
</template>

<script>
export default {
    name: 'my-button',
}
</script>

<style>
.button_form {
    align-self: flex-end;
    margin: 10px;
    padding: 10px 15px;
    background: none;
    color: #002c85;
    border: 2px solid #002c85;
}
</style>

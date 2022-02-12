<template>
    <button
        :disabled="disabled"
        class="ptd-button"
        @click="$emit('clicked')"
        :type="type"
    > {{text}}
    </button>
</template>

<script>

export default {
    props: {
        type: {
            type: String,
            default: 'button'
        },

        text: {
            type: String,
            default: ''
        },

        disabled: {
            type: Boolean,
            default: false
        },
    },
};
</script>
<style lang="scss" scoped>

</style>

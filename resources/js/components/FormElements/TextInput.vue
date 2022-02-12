<template>
    <div class="text-input-container">
        <label class="text-label">
            {{ label }}
        </label>
        <input
            class="text-input"
            :type="varient"
            :value="value"
            :name="name"
            :placeholder="placeholder"
            @keyup="keyPressed"
        />
    </div>
</template>

<script>
export default {
    name: "TextInput",

    props: {
        label: {
            type: String
        },
        value: {
            type: String | Number
        },
        varient: {
            type: String,
            required: true
        },
        name: {
            type: String,
            required: true
        },
        placeholder: {
            type: String
        },
    },

    methods: {
        keyPressed(e) {
            this.$emit('typing', e.target.value);
        }
    },
}

</script>

<style lang="scss" scoped>

.text-input-container {
    display: flex;
    flex-direction: column;
    text-align: start;
    margin-left: 30px;
    padding-top: 30px;
}

.text-label {
    font-size: 24px;
    margin-bottom: 10px;
    line-height: 20px;
    color: white;
}

.text-input {
    width: 545px;
    height: 44px;
    padding: 10px 20px 10px 12px;
    background-color: #F6F7F7;
    border: 2px solid #ECEEEF;
    border-radius: 4px;
    font-weight: 300;
    font-size: 14px;
    line-height: 20px;
    &:focus {
        outline: none;
        border: 2px solid #5041d7;
    }

    &::placeholder {
        color: #627177;
    }

    &::-ms-input-placeholder {
        color: #627177;
    }
}
</style>

<template>
    <label class="label">{{ label }}</label>
    <textarea name="" id="" cols="30" rows="10" :value="modelValue" :placeholder="placeholder" :required="required"
        @input="$emit('update:modelValue', $event.target.value)"></textarea>
    <p v-if="errorMessage === ''">{{ hintMessage }}</p>
    <p class="error">{{ errorMessage }}</p>
</template>
<script>
export default {
    props: {
        label: {
            type: [String],
            default: ""
        },
        placeholder: {
            type: String,
            default: ""
        },
        required: {
            type: Boolean,
            default: false
        },

        hintMessage: {
            type: String,
            default: ""
        },
        errorMessage: {
            type: String,
            default: ""
        },
        modelValue: {
            type: [String, Number,],
            default: ""
        }
    },

}
</script>

<style scoped>
textarea {
    width: 15rem;
    height: 40px;
    border-radius: 4px;
    border: 2px solid black;

}
</style>
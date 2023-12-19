<template>
    <div class="container">
        <label class="label">{{ label }}</label>
        <input :type="type" :required="required" :placeholder="placeholder" :value="modelValue"
            @input="$emit('update:modelValue', $event.target.value)">
        <p v-if="errorMessage === ''">{{ hintMessage }}</p>
        <p class="error">{{ errorMessage }}</p>
    </div>
</template>
<script>
export default {


    props: {
        label: {
            type: String,
            default: ""
        },
        type: {
            type: String,
            default: "text"
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
input {
    width: 15rem;
    height: 40px;
    border-radius: 6px;
    border: 1px solid black;

}
</style>
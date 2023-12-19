<template>
    <div class="container">

        <label class="label">{{ label }}</label>
        <select name="" id="" :required="required" :value="modelValue"
            @input="$emit('update:modelValue', $event.target.value)">
            <option v-for="option in options"> {{ option }}</option>
        </select>
        <p v-if="errorMessage === ''">{{ hintMessage }}</p>
        <p class="error">{{ errorMessage }}</p>
    </div>
</template>
<script>
export default {
    props: {
        label: {
            type: String,
            default: "Choose:"
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
            type: [String, Number],
            default: ""
        },
        options: {
            type: [String, Array],
            default: ""
        }
    }
}
</script>
<style scoped>
select {
    width: 15rem;
    height: 40px;
    border-radius: 4px;
    border: 2px solid black;

}
</style>
<template>
    <div class="container">
        <label class="label">
            <input type="radio" :value="value" v-model="model">
            {{ label }}
        </label>

    </div>
</template>
<script>
export default {
    props: {

        label: {
            type: String
        },
        options: {
            type: Array
        }, modelValue: {
            type: [Array, Boolean],
        },
        value: {
            type: [String, Array],
        },
    },
    computed: {
        model: {
            get() {
                return this.modelValue;
            },
            set(value) {
                this.$emit("update:modelValue", value);
            },
        },
    },

}
</script>

<style scoped>
.container {
    width: 60%;
    margin: 20px auto;
    padding: 15px 20px;
    border: 1px solid black;
    border-radius: 8px;

    display: flex;
    justify-content: space-between;
}
</style>
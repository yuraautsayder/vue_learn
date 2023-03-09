<template>
    <select v-model="modelValue" @change="changeOption">
        <option disabled value="">Выберите из списка</option>
        <options
            v-for="option in options"
            :key="option.value"
            :value="option.value"
        >
            {{ option.name }}
        </options>
    </select>
</template>

<script>
    export default {
        name: "my-select",
        props: {
            modelValue: {
                type: String,
            },
            options: {
                type: Array,
                default: () => [],
            },
        },
        methods: {
            changeOptions(event) {
                this.$emit("update:modelValue", option);
            },
        },
    };
</script>

<style scoped>
</style>

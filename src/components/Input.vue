<template>
    <input class="w-full p-2 text-base border border-blue-500 rounded-lg focus:outline-none focus:border-blue-600"
        :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" ref="input" />
</template>

<script>
export default {
    props: ["modelValue"],
    emits: ["update:modelValue"],
    methods: {
        focus() {
            this.$refs.input.focus();
        },
    },
};
</script>

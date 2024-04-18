<script lang="ts">
export default {
    name: 'ButtonDefault',
    props: {
        isDisabled: { type: Boolean, default: false },
        text: { type: String, required: true, default: '' },
        icon: { type: String, required: true, default: '' }
    },
    emits: ['click'],
    methods: {
        method(): void {
            this.$emit('click')
        }
    }
}
</script>

<template>
    <button class="button" @click="method" v-bind:disabled="isDisabled">
        <span class="icon">
            <i v-bind:class="icon"></i>
        </span>
        <span>{{ text }}</span>
    </button>
</template>
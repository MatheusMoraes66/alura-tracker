<script lang="ts">

export default {
    name: 'TaskTimer',
    props: {
        seconds: { type: Number, required: true }
    },
    computed: {
        timer(): string {
            return new Date(this.seconds * 1000).toISOString().slice(11, 19);
        }
    }
}
</script>

<template>
    <section>
        <strong class="has-text-grey">{{ timer }}</strong>
    </section>
</template>
<script lang="ts">
import ToggleSwitch from './ToggleSwitch.vue';

export default {
    name: 'SideBar',
    components: { ToggleSwitch },
    methods: {
        changeDarkmode(checked: boolean) {
            this.$emit('darkmode', checked)
        }
    },
    emits: ['darkmode']
}
</script>

<template>
    <header>
        <div class="container">
            <img src="../assets/logo.png" alt="Alura Tracker">
        </div>
        <div class="dark-mode">
            <div class="is-flex is-justify-content-space-between ">
                <p class="has-text-white">Dark mode </p>
                <ToggleSwitch @is-checked="changeDarkmode" />
            </div>
        </div>
    </header>
</template>

<style scoped>
header {
    position: relative;
    background: #0d3b66;
    width: 100%;
    height: 100vh;
}

.container {
    padding: 1rem;
}

.dark-mode {
    width: 100%;
    bottom: 0;
    position: absolute;
    display: block;
    padding: 10px;
}

@media only screen and (max-width: 768px) {
    header {
        padding: 0.5rem;
        height: auto;
        display: flex;
        justify-content: space-between;
    }

    .container img {
        width: 200px;
    }

    .dark-mode {
        position: relative;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }

    .dark-mode p {
        display: none;
    }
}
</style>
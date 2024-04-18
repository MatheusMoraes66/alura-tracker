<script lang="ts">
import ButtonDefault from './ButtonDefault.vue';
import TaskTimer from './TaskTimer.vue';

export default {
    name: 'StopwatchTask',
    data() {
        return {
            intervalId: 0,
            seconds: 0
        }
    },
    methods: {
        clearStates() {
            this.intervalId = 0;
            this.seconds = 0;
            this.$emit('clearDescription')
        },
        playTimer() {
            this.intervalId = setInterval(() => {
                this.seconds += 1;
            }, 1000);
        },
        stopTimer() {
            clearInterval(this.intervalId);
            this.$emit('markTime', this.seconds);
            this.clearStates();
        }
    },
    emits: ['markTime', 'clearDescription'],
    components: { TaskTimer, ButtonDefault }
}
</script>

<template>
    <div class="is-flex is-align-items-center is-aling-center is-justify-content-space-between">
        <TaskTimer :seconds="seconds" />
        <ButtonDefault :text="'play'" :icon="'fas fa-play'" :is-disabled="intervalId != 0" @click="playTimer" />
        <ButtonDefault :text="'stop'" :icon="'fas fa-stop'" :is-disabled="intervalId == 0" @click="stopTimer" />
        <ButtonDefault :text="'eraser'" :icon="'fas fa-eraser'" :is-disabled="false" @click="clearStates" />
    </div>
</template>
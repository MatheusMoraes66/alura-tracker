<script lang="ts">
import type ITask from '@/interfaces/ITask';
import type { PropType } from 'vue';
import TaskCard from './TaskCard.vue';

export default {
    name: 'TaskList',
    props: {
        tasks: { type: [] as PropType<Array<ITask>> }
    },
    components: { TaskCard }
}
</script>

<template>
    <div class="fixed-grid m-4">
        <div class="grid">
            <div class="cell" v-for="(task, index) in tasks" v-bind:key="index">
                <TaskCard :task="task" />
            </div>
        </div>
    </div>
</template>
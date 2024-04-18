<script lang="ts">
import type ITask from '@/interfaces/ITask';
import TaskTimer from './TaskTimer.vue';
import type { PropType } from 'vue';


export default {
    name: 'TaskCard',
    props: {
        task: { type: Object as PropType<ITask>, required: true }
    },
    components: { TaskTimer }
}
</script>

<template>
    <div class="card">
        <div class="card-content">
            <p class="title">
                {{ task.description }}
            </p>
        </div>
        <footer class="card-footer">
            <p class="card-footer-item">
                <TaskTimer :seconds="Number(task.timer)" />
            </p>
        </footer>
    </div>
</template>
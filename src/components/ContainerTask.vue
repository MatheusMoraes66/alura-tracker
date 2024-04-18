<script lang="ts">
import type ITask from '@/interfaces/ITask';
import StopwatchTask from './StopwatchTask.vue';
import TaskList from './TaskList.vue';
import EmptyList from './EmptyList.vue'

export default {
    name: 'ContainerTask',
    data() {
        return {
            tasks: [] as Array<ITask>,
            description: '' as String,
        }
    },
    computed: {
        isEmpty(): boolean {
            return this.tasks.length > 0
        }
    },
    methods: {
        addTask(timer: number) {
            this.tasks.push({
                description: this.description,
                timer: timer
            });
        },
        clearDescription() {
            this.description = '';
        }
    },
    components: { StopwatchTask, TaskList, EmptyList }
}
</script>

<template>
    <div class="box m-4">
        <div class="columns ">
            <div class="column is-8" role="form" aria-label="Formulario para criação de uma nova tarefa">
                <div class="field">
                    <p class="control has-icons-left has-icons-right">
                        <input class="input" type="text" placeholder="Descreva a sua tarefa" v-model="description"
                            v-bind:on-focus="description.length > 0" />
                        <span class="icon is-small is-left">
                            <i class="fas fa-pen"></i>
                        </span>
                    </p>
                </div>

            </div>
            <div class="column">
                <StopwatchTask @mark-time="addTask" @clear-description="clearDescription" />
            </div>
        </div>
    </div>
    <TaskList :tasks="tasks" v-if="isEmpty" />
    <EmptyList v-else />

</template>
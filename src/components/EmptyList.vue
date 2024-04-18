<script lang="ts">
export default {
    name: 'EmptyList'
}
</script>

<template>
    <div class="list-container">
        <div class="columns is-half is-flex is-flex-direction-column">
            <div class="column mr-auto ml-auto">
                <span class="icon is-large has-text-grey-lighter">
                    <i class="fas fa-list fa-5x"></i>
                </span>
            </div>
            <div class="column is-size-4 has-text-grey-lighter">
                A lista de tarefas está vazia.
            </div>
        </div>
    </div>
</template>

<style scoped>
.list-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 80%;
}

@media only screen and (max-width: 768px) {
    .list-container {
        margin-top: 5rem;
    }
}
</style>
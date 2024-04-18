<script lang="ts">
import ContainerTask from './components/ContainerTask.vue';
import Sidebar from './components/Sidebar.vue';

export default {
  components: { Sidebar, ContainerTask },
  data() {
    return {
      theme: false
    }
  },
  computed: {
    istheme() {
      return this.theme ? 'theme-dark' : 'theme-light has-background-white'
    }
  },
  methods: {
    changeTheme(value: boolean) {
      this.theme = value;
    }
  }
}
</script>

<template>
  <main v-bind:class="istheme" style="height: 100vh;">
    <div class="columns is-gapless">
      <div class="column is-2">
        <Sidebar @darkmode="changeTheme" />
      </div>
      <div class="column auto">
        <ContainerTask />
      </div>
    </div>
  </main>
</template>

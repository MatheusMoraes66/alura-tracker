<script lang="ts">
export default {
    name: 'ToggleSwitch',
    data() {
        return {
            checked: false
        }
    },
    methods: {
        checkboxChanged() {
            this.$emit('isChecked', this.checked);
        }
    },
    emits: ['isChecked']
}
</script>

<template>
    <label class="toggle-switch">
        <input type="checkbox" v-model="checked" @change="checkboxChanged">
        <span class="slider"></span>
    </label>
</template>

<style scoped>
.toggle-switch input {
    display: none;
}

.slider {
    position: relative;
    display: inline-block;
    width: 40px;
    height: 20px;
    background-color: #ccc;
    border-radius: 34px;
    transition: background-color 0.3s;
}


.slider:before {
    position: absolute;
    content: "";
    height: 20px;
    width: 20px;
    left: 0px;
    bottom: 0px;
    background-color: white;
    border-radius: 50%;
    transition: transform 0.3s;
}

input:checked+.slider {
    background-color: #2196F3;
}

input:checked+.slider:before {
    transform: translateX(26px);
}
</style>
<script setup lang="ts">

defineProps([
    'options',
    'label',
    'width'
])

const model = defineModel()

</script>

<template>
    <div class="content-select" :style="{width: width}">
        <label>{{label}}</label>
        <select v-model="model">
            <option v-for="option in options">{{option}}</option>
        </select>
    </div>
</template>

<style scoped lang="scss">
.content-select{
    display: flex;
    flex-direction: column;
    gap: 5px;

    label {
        font-weight: bold;
    }

    select{
        padding: 6px 8px;
        font-size: 14px;
        border-radius: 6px;
        border: 0;
        border-bottom: 2px solid #CCC;
        border-left: 2px solid #CCC;
        background-color: #EEEEEE;


        &:focus, &:focus-visible, &:hover{
            border-bottom: 2px solid blueviolet;
            border-left: 2px solid blueviolet;
            outline: none;
        }

    }
}

</style>
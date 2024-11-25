<script setup lang="ts">
const props = defineProps({
    label: String,
    type: String,
    width: String,
    name: String,
    placeholder: String
})

const model = defineModel()


</script>

<template>
    <div class="content-text" :style="{width: width}">
        <label>{{label}}</label>
        <input :type="type" :name :placeholder v-model="model"/>
    </div>
</template>

<style scoped lang="scss">
.content-text {
    display: flex;
    flex-direction: column;
    gap: 5px;
    label{
        font-weight: bold;
    }
    input{
        padding: 6px 12px;
        font-size: 14px;
        border-radius: 6px;
        border: 0;
        border-bottom: 2px solid #CCC;
        border-left: 2px solid #CCC;
        background-color: #EEE;

        &:focus {
            border-bottom: 2px solid blueviolet;
            border-left: 2px solid blueviolet;
            background-color: rgba(138, 43, 226, 0.29);
            outline: none;
            color: blueviolet;
        }
    }
}
</style>
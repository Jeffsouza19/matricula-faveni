<script setup lang="ts">
defineProps([
    'value'
])
</script>

<template>
    <div>
        <label></label>
        <input type="button" :value="value"/>
    </div>
</template>

<style scoped lang="scss">
input{
    padding: 6px 8px;
    border-radius: 6px;
    border: 2px solid #CCCCCC;
    background-color: #EEEEEE;
    transition: all .2s ease-in-out;
    color: #666666;
    font-size: 15px;
    font-weight: bold;

    &:active{
        border: 2px solid blueviolet;
        background-color: rgba(138, 43, 226, 0.29);
        color: blueviolet;
    }
}
</style>
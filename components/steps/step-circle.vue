<script setup lang="ts">

defineProps([
    'steps'
])
const selectedItem = ref(null)

const setActive = (index) => {
    selectedItem.value = index
}
</script>

<template>
    <div class="container-step">
        <div v-for="(step, index) in steps"
             class="content-step" :key="index + 1"
             :style="{
                 backgroundColor: selectedItem === index ? 'rgba(138, 43, 226, 0.29)':'',
                 borderColor: selectedItem === index ? 'blueviolet' : ''
             }"
             @click="setActive(index)"
        >
            <div>
                <h3 :style="{
                    color: selectedItem === index ? 'blueviolet': ''
                }">
                    {{index + 1}}
                </h3>
            </div>
            <span>{{step}}</span>
        </div>
    </div>
</template>

<style scoped lang="scss">
.container-step{
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    margin-bottom: 40px;
}
.content-step{
    position: relative;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    border: 2px solid #CCC;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;

    div {
        h3 {
            color: #AAA;
        }
    }
    span {
        position: absolute;
        top: 50px;
        text-align: center;
        color: #666;
    }
}
</style>
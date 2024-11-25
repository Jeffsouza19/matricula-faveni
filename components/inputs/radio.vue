<script setup lang="ts">
defineProps([
    'values',
    'label',
    'name'
])
</script>

<template>
    <div class="content">
        <label>{{label}}</label>
        <div class="content-radio">
            <label v-for="value in values">
                <input type="radio" value="{{value}}" name="{{name}}"/>
                <p>{{value}}</p>
            </label>
        </div>
    </div>
</template>

<style scoped>
.content{
    display: flex;
    flex-direction: column;
}

.content-radio{
    display: flex;
    label{
        margin: 5px;
        display: flex;
        align-items: center;
        input{
            appearance: none;
            height: 1.25em;
            position: relative;
            width: 1.25em;

            &:before, &:after{
                border-radius: 50%;
                position: absolute;
            }

            &:after {
                background-color: blueviolet;
                content: '';
                height: 50%;
                left: 25%;
                transform: scale(0);
                transform-origin: center;
                transition: transform 0.7s;
                top: 15%;
                width: 50%;
            }

            &:before {
                border: 2px solid #CCC;
                box-sizing: border-box;
                content: '';
                height: 100%;
                width: 100%;
                bottom: 10%;
            }


            &:checked::after {
                transform: scale(1);
            }

            &:checked::before {
                border-color: blueviolet;
            }
        }
    }
}
</style>
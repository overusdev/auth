<template>
    <button
        class="button"
        @click="onClick"
    >
        {{ label }}
    </button>
</template>

<script setup lang="ts">
import { defineProps, defineEmits } from 'vue';
import type { Props } from './types/props';

const emit = defineEmits(['click']);

defineProps<Props>();

function onClick () {
    emit('click');
}

</script>

<style lang="scss" scoped>
.button {
    outline: none;
    border: none;
    padding: 16px;
    font-size: 16px;
    background: #0084ff;
    color: #fff;
    transition: all .3s ease-in-out;

    @media (min-width: 1024px) {
        cursor: pointer;

        &:hover {
            background: #2c99ff;
        }
    }
}
</style>
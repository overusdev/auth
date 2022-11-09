<template>
    <div class="input">
        <input
            class="input__field"
            :placeholder="placeholder"
            @focus="setFocus"
            @blur="resetFocus"
            @input="updateValue($event)"
        >
    </div>
</template>

<script setup lang="ts">
import { ref, defineProps, defineEmits } from 'vue';
import type { Props } from './types/props';

const emit = defineEmits(['update.modelValue']);
const isActive = ref<boolean>(false);

const props = defineProps<Props>();

function updateValue (event) {
    emit('update.modelValue', event.target.value);
}

function setFocus () {
    isActive.value = true;
}

function resetFocus () {
    if(!props.modelValue) {
        isActive.value = false;
    }
}

</script>

<style lang="scss" scoped>
.input {

    &__field {
        padding: 12px;
        box-sizing: border-box;
        width: 100%;
        border: none;
        outline: none;
        border-bottom: 1px solid #4e4e4e;
        transition: all .3s ease-in-out;

        @media (min-width: 1024px) {
            cursor: pointer;
        }
    }

}
</style>
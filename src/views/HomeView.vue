<template>
    <div class="main">
        <AuthForm
            v-if="isShowForm"
            class="main__auth-form"
            @click="hideForm"
        />
        <Button
            v-if="!isShowForm"
            label="Show auth form"
            class="main__button"
            @click="showForm"
        />
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import Button from '@/components/Button/Button.vue';
import AuthForm from '@/components/AuthForm/AuthForm.vue';

const isShowForm = ref<boolean>(false);

function showForm() {
    isShowForm.value = !isShowForm.value;
}

function hideForm() {
    isShowForm.value = false;
}
</script>

<style lang="scss" scoped>
.main {
    padding: 16px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    @media (min-width: 1024px) {
        padding: 0;
    }
}
</style>
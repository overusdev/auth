<template>
    <div class="main">
        <Button
            label="Show auth form"
            @click="showForm"
        />
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import Button from '@/components/Button/Button.vue';

const isShowForm = ref<boolean>(false);

function showForm() {
    console.log('showForm');
    isShowForm.value = true;
}
</script>
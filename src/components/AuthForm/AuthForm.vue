<template>
    <div 
        class="auth-form"
    >
        <IconClose
            class="auth-form__icon-close"
            @click="closeForm"
        />

        <pre>
            {{ formData }}
        </pre>

        <Input
            placeholder="Enter your e-mail"
            class="auth-form__input"
            v-model.modelValue="formData.email"
        />

        <Input
            placeholder="Enter your password"
            type="password"
            class="auth-form__input"
            v-model.modelValue="formData.password"
        />

        <Input
            placeholder="Confirm your password"
            type="password"
            class="auth-form__input"
            v-model.modelValue="formData.confirmedPassword"
        />

        <Button
            label="Send"
            isWide
        />

    </div>
</template>

<script setup lang="ts">
import { ref, reactive, defineProps, defineEmits } from 'vue';
import IconClose from '@/components/icons/IconClose.vue'
import Button from '@/components/Button/Button.vue';
import Input from '@/components/Input/Input.vue';
import type { Props } from './types/props';

defineProps<Props>();
const emit = defineEmits(['click']);
const formData = reactive({
    email: '',
    password: '',
    confirmedPassword: ''
});

function closeForm() {
    emit('click');
}

</script>

<style lang="scss" scoped>
.auth-form {
    width: 100%;
    padding: 36px 16px;
    -webkit-box-shadow: 0px 2px 10px 0px rgba(50, 50, 50, 0.41);
    -moz-box-shadow:    0px 2px 10px 0px rgba(50, 50, 50, 0.41);
    box-shadow:         0px 2px 10px 0px rgba(50, 50, 50, 0.41);

    @media (min-width: 1024px) {
        width: 350px;
    }

    &__icon-close {
        position: absolute;
        right: 16px;
        top: 16px;

        @media (min-width: 1024px) {
            cursor: pointer;
        }
    }

    &__input {
        margin-bottom: 24px;
    }

}
</style>
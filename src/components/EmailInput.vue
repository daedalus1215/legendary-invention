<template>
    <input type="email" class="form-control" placeholder="E-mail" :value="email" @input="update($event)" :class="{
        'is-valid': validateEmail(email),
        'is-invalid': !validateEmail(email),
    }" />
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';
import validateEmail from './validate-email';

const props = defineProps({
    email: String
});

const emit = defineEmits(['update:email']);

function update(event) {
    emit('update:email', event.target.value);
}

</script>

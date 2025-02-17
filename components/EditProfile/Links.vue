<script setup>
import { updateLinks } from '~/composable/useUpdate';
import { useUser } from '~/composable/useUser';
const user = useUser()

const links = JSON.parse(user?.value?.links)

const inputs = ["instagram", "linkedin", "twitter", "other"];
</script>
<template>
    <form @submit.prevent="updateLinks">
        <div class="text-lg py-2 font-medium">Add your social links</div>
        <div v-for="input in inputs" class="mb-4">
            <label class="text-sm capitalize">{{ input }}</label>
            <input type="text" class="w-full" :name="input" :value="links[input]">
        </div>
        <button class="text-sm bg-primary px-4 py-2 rounded mb-5"> Update </button>
    </form>
</template>
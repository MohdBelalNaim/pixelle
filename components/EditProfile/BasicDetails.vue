<script setup>
import { updateBasicDetails } from '~/composable/useUpdate';
import { useUser } from '~/composable/useUser';
const user = useUser()

const inputs = ["name", "city", "state", "bio"]
console.log(user?.value);
</script>
<template>
    <form @submit.prevent="updateBasicDetails">
        <div class="text-lg py-2 font-medium">Basic details</div>
        <div v-for="input in inputs" class="mb-4">
            <label class="text-sm capitalize">{{ input }}</label>
            <input :value="user[input]" type="text" class="w-full" :name="input" />
        </div>
        <button class="text-sm bg-primary px-4 py-2 rounded mb-5"> Update </button>
    </form>
</template>
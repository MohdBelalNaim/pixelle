<script setup lang="ts">
import { updatePassword } from "~/composable/useUpdate"
import { useUser } from "~/composable/useUser";
const user = useUser()
</script>
<template>
    <form @submit.prevent="updatePassword">
        <div class="text-lg py-2 font-medium">Change password</div>

        <label for="" class="text-sm">Enter current password</label>
        <input type="password" class="w-full mb-2" name="current" required>

        <label for="" class="text-sm">Enter new password</label>
        <input type="password" class="w-full" name="password" required>
        <button class="text-sm bg-primary px-4 py-2 rounded mt-2"> Update </button>
    </form>
</template>
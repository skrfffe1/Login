<script setup>
import { ref } from 'vue';
import SignInButton from '../components/SignInButton.vue';
import RegisterButton from '../components/RegisterButton.vue';
import RegisterView from '../components/RegisterView.vue';
import LoginView from '../components/LoginView.vue';

name: 'HomeView';

const isVisible = ref(true)

</script>

<template>
    <div class="grid grid-rows-1 mt-16">

        <div class="flex flex-row gap-4">

            <div class="grid grid-cols-2 gap-4 mr-16 outline-gray-700 box-border h-64 w-64 flex-auto rounded-lg outline-dashed
                outline-2 outline-offset-2">
                <div class="grid grid-cols-1 gap-4 place-items-center">
                    <div class="">
                        <SignInButton @click="isVisible = true" />
                        <RegisterButton @click="isVisible = false" />
                    </div>
                </div>
                <div>

                </div>
            </div>

            <div class="box-border h-64 flex-auto w-32">
                <LoginView v-if="isVisible" />
                <RegisterView v-else />
            </div>
        </div>
    </div>
</template>
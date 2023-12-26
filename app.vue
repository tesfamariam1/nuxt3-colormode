<script setup lang="ts">
const colorMode = useColorMode();
const changeColor = () => (colorMode.preference = (colorMode.value === 'light' ? 'dark' : 'light'))

</script>

<template>
    <div class="dark:bg-black bg-white min-h-screen flex-wrap">
        <nav class="flex items-center justify-between flex-wrap p-6">
            <div class="flex items-center flex-shrink-0 text-black dark:text-white mr-6">
                <span class="font-semibold text-xl tracking-tight">Nuxt ColorMode</span>
            </div>
            <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
                <div class="text-sm lg:flex-grow">
                    <nuxt-link to="/" class="block mt-4 lg:inline-block lg:mt-0 dark:text-teal-200 text-gray-500 dark:hover:text-white mr-4">
                        Home
                    </nuxt-link>
                    <nuxt-link to="/" class="block mt-4 lg:inline-block lg:mt-0 dark:text-teal-200 text-gray-500 dark:hover:text-white mr-4">
                        About
                    </nuxt-link>
                    <nuxt-link to="/" class="block mt-4 lg:inline-block lg:mt-0 dark:text-teal-200 text-gray-500 dark:hover:text-white">
                        Contact
                    </nuxt-link>
                </div>
                <div>
                    <button aria-label="Color Mode" class="inline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent bg-teal-800 dark:bg-white mt-4 lg:mt-0"
                            @click="changeColor">
                        <ColorScheme placeholder="...">
                            <Icon v-if="colorMode.value === 'dark'" name="heroicons-outline:moon" class="text-xl text-black" />
                            <Icon v-else name="heroicons-outline:sun" class="text-xl" />
                        </ColorScheme>
                    </button>
                </div>
            </div>
        </nav>
    </div>
</template>

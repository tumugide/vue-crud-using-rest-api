<script setup>
    import { reactive } from 'vue';
    import useSkills from '../../composable/skills';

    const { storeSkill,errors } = useSkills();
    const form = reactive({
        name: "",
        slug: ""
    });
</script>
<template>
    <div class="mt-12">
        <form class="max-w-md mx-auto p-4 bg-white dark:bg-slate-700 shadow-md rounded-md" @submit.prevent="storeSkill(form)">
            <div class="space-y-6">
                <div class="mb-6">
                    <label for="name"
                        class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Name</label>
                    <input type="text" id="name" v-model="form.name" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                    <div v-if="errors.name">
                        <span class="tex-sm text-red-400">
                            {{ errors.name[0] }}
                        </span>
                    </div>
                </div>
                <div class="mb-6">
                    <label for="slug"
                        class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Slug</label>
                    <input type="text" id="slug" v-model="form.slug" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                    <div v-if="errors.slug">
                        <span class="tex-sm text-red-400">
                            {{ errors.slug[0] }}
                        </span>
                    </div>
                </div>
                <div class="mt-4">
                    <button
                        class="py-2 px-4 bg-indigo-700 dark:bg-indigo-600 rounded hover:bg-indigo-600 dark:hover:bg-indigo-700">Store</button>
                </div>
            </div>
        </form>
    </div>
</template>
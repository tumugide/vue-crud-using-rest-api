<script setup>
import useSkills from '../../composable/skills';
import { onMounted } from 'vue';

const { skills, getSkills, destroySkill } = useSkills();

onMounted(() => getSkills());
</script>
<template>
    <div class="mt-12">
        <div class="flex justify-end m-2 p-2">
            <RouterLink :to="{ name: 'SkillCreate'}" class="py-2 px-4 bg-indigo-700 dark:bg-indigo-600 rounded hover:bg-indigo-600 dark:hover:bg-indigo-700">New Skill</RouterLink>
        </div>

        <div class="overflow-x-auto relative">
            <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
                <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                    <tr>
                        <th scope="col" class="py-3 px-6">
                            Name
                        </th>
                        <th scope="col" class="py-3 px-6">
                            Slug
                        </th>
                        <th scope="col" class="py-3 px-6">
                            Action
                        </th>

                    </tr>
                </thead>
                <tbody>
                    <tr v-for="skill in skills" :key="skill.id"
                        class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
                        <td class="py-4 px-6">
                            {{ skill.name }}
                        </td>
                        <td class="py-4 px-6">
                            {{ skill.slug }}
                        </td>
                        <td class="py-4 px-6 space-x-2">
                            <RouterLink :to="{name: 'SkillEdit', params: {id: skill.id}}" class="py-2 px-4 bg-green-700 dark:bg-green-600 rounded hover:bg-green-600 dark:hover:bg-green-700 text-white">Edit</RouterLink>
                            <button @click="destroySkill(skill.id)" class="py-2 px-4 bg-red-700 dark:bg-red-600 rounded hover:bg-red-600 dark:hover:bg-red-700 text-white">
                                Delete
                            </button>
                        </td>
                    </tr>

                </tbody>
            </table>
        </div>

    </div>
</template>
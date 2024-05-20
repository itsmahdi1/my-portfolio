<template>
    <Head title="Skills" />
    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Skills
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="flex justify-end m-2 p-2">
                    <Link
                        :href="route('skills.create')"
                        class="px-4 py-2 bg-indigo-500 hover:bg-indigo-700 text-white rounded-md"
                    >
                        New Skill
                    </Link>
                </div>
                <div class="relative overflow-x-auto">
                    <table class="w-full text-sm text-left rtl:text-right text-gray-500">
                        <thead class="text-xs text-gray-700 uppercase bg-gray-50">
                            <tr>
                                <th scope="col" class="px-6 py-3">ID</th>
                                <th scope="col" class="px-6 py-3">Name</th>
                                <th scope="col" class="px-6 py-3">Image</th>
                                <th scope="col" class="px-6 py-3">Actions</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="skill in skillsData" :key="skill.id" class="bg-white border-b">
                                <th scope="row" class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap">
                                    {{ skill.id }}
                                </th>
                                <td class="px-6 py-4">{{ skill.name }}</td>
                                <td class="px-6 py-4">
                                    <img :src="skill.image"
                                    alt=""
                                    class="h-12 w-12 object-cover"
                                    />
                                </td>
                                <td class="px-6 py-4">
                                    <Link :href="route('skills.edit', skill.id)" method="get" as="button" type="button" class="font-medium text-blue-500 hover:text-blue-700 mr-2">Edit</Link>
                                    <Link :href="route('skills.destroy', skill.id)" method="delete" class="font-medium text-red-500 hover:text-red-700 mr-2">Delete</Link>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>


<script>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import { computed } from 'vue';

export default {
    components: {
        Head,
        Link,
        AuthenticatedLayout,
    },
    props: {
        skills: {
            type: Object,
            required: true,
            default: () => ({ data: [] })
        }
    },
    setup(props) {
        // Ensure props.skills is always an object and has a data property
        const skillsData = computed(() => {
            return (props.skills && props.skills.data) ? props.skills.data : [];
        });

        return { skillsData };
    }
};
</script>

<style scoped>
/* Add any required styles here */
</style>


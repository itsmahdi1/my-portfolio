<template>
    <Head title="Add Skill" />
    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Add Skill
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <form @submit.prevent="form.post('/login')">
                    <!-- email -->
                    <input type="text" v-model="form.name" />
                    <div v-if="form.errors.name">{{ form.errors.name }}</div>
                    <!-- password -->
                    <input type="file" @input="form.image = $event.target.files[0]" />
                    <div v-if="form.errors.image">
                        {{ form.errors.image }}
                    </div>

                    <!-- submit -->
                    <button type="submit" :disabled="form.processing">
                        Store
                    </button>
                </form>
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<script>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, useForm } from "@inertiajs/vue3";
export default {
    components: {
        Head,
        useForm,
        AuthenticatedLayout,
    },
    setup() {
        const form = useForm({
            name: '',
            image: null,
        });

        return { form };
    },
};
</script>

<script setup>
import { ref } from "vue";
import { useForm } from "@inertiajs/inertia-vue3";

const showMessage = ref(false);

const form = useForm({
    name: "",
    email: "",
    body: "",
});

function setShowMessage(value) {
    showMessage.value = value;
}

function cleanForm() {
    // Log to verify this function is called
    console.log("cleanForm function called");

    // Reset form fields
    form.reset();

    // Set showMessage to true
    setShowMessage(true);

    // Log to verify showMessage is set to true
    console.log("Form reset and showMessage set to true");

    // Hide message after 3000ms
    setTimeout(() => {
        setShowMessage(false);
        // Log to verify showMessage is set to false
        console.log("showMessage set to false");
    }, 3000);
}

const submit = () => {
    console.log("Submit function called");
    form.post(route("contact"), {
        preserveScroll: true,
        onSuccess: () => cleanForm(),
    });
};
</script>

<template>
    <section class="section bg-light-primary dark:bg-dark-primary">
        <div class="container mx-auto">
            <div class="flex flex-col items-center text-center">
                <h2 class="section-title">Contact Me</h2>
                <p class="subtitle">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Fuga veniam labore nisium illum cupiditate reiciendis a
                    numquam
                </p>
            </div>
            <div class="flex flex-col lg:flex-row lg:gap-x-8">
                <div
                    class="flex flex-1 flex-col items-start space-y-8 mb-12 lg:mb-0 lg:pt-2"
                >
                    <!-- Your contact info section here -->
                </div>
                <form
                    @submit.prevent="submit"
                    class="space-y-8 w-full max-w-md"
                >
                    <div
                        v-if="showMessage"
                        class="m-2 p-4 bg-light-tail-500 dark:bg-dark-navy-100 text-light-secondary rounded-lg"
                    >
                        Thank you for contacting me.
                    </div>
                    <div class="flex gap-8">
                        <div>
                            <input
                                v-model="form.name"
                                type="text"
                                class="input"
                                placeholder="Your Name"
                            />
                            <span
                                v-if="form.errors.name"
                                class="text-sm m-2 text-red-400"
                                >{{ form.errors.name }}</span
                            >
                        </div>
                        <div>
                            <input
                                v-model="form.email"
                                type="email"
                                class="input"
                                placeholder="Your Email"
                            />
                            <span
                                v-if="form.errors.email"
                                class="text-sm m-2 text-red-400"
                                >{{ form.errors.email }}</span
                            >
                        </div>
                    </div>
                    <textarea
                        v-model="form.body"
                        class="textarea"
                        placeholder="Your Message"
                        spellcheck="false"
                    ></textarea>
                    <span
                        v-if="form.errors.body"
                        class="text-sm m-2 text-red-400"
                        >{{ form.errors.body }}</span
                    >
                    <button
                        class="btn btn-lg bg-accent hover:bg-secondary text-white"
                    >
                        Send message
                    </button>
                </form>
            </div>
        </div>
    </section>
</template>

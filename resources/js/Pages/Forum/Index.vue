<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import ForumLayout from "@/Layouts/ForumLayout.vue";
import { Head } from "@inertiajs/vue3";
import Select from "@/Components/Select.vue";
import InputLabel from "@/Components/InputLabel.vue";

defineProps(["topics"]);
</script>

<template>
    <Head title="Forum" />

    <ForumLayout>
        <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
            <div class="p-6 text-gray-900">
                <div>
                    <InputLabel for="topic" value="Topic" class="sr-only" />
                    <Select id="topic">
                        <option value="">All topics</option>
                        <option
                            :value="topic.slug"
                            v-for="topic in topics"
                            :key="topic.id"
                        >
                            {{ topic.name }}
                        </option>
                    </Select>
                </div>
            </div>
        </div>
        <template #side>
            <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                <div class="p-6 text-gray-900">Side</div>
            </div>
        </template>
    </ForumLayout>
</template>

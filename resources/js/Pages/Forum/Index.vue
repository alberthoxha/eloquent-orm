<script setup>
import ForumLayout from "@/Layouts/ForumLayout.vue";
import { Head } from "@inertiajs/vue3";
import Select from "@/Components/Select.vue";
import InputLabel from "@/Components/InputLabel.vue";
import Discussion from "@/Components/Forum/Discussion.vue";
import Pagination from "@/Components/Pagination.vue";

defineProps({
    topics: Array,
    discussions: Object,
});
</script>

<template>
    <Head title="Forum" />
    <ForumLayout>
        <div class="space-y-6">
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
                                {{ topic.title }}
                            </option>
                        </Select>
                    </div>
                </div>
            </div>
            <div class="space-y-3">
                <template v-if="discussions.data.length">
                    <Discussion
                        v-for="discussion in discussions.data"
                        :key="discussion.id"
                        :discussion="discussion"
                    />
                    <Pagination :pagination="discussions.meta" />
                </template>
            </div>
        </div>

        <template #side>
            <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                <div class="p-6 text-gray-900">Side</div>
            </div>
        </template>
    </ForumLayout>
</template>

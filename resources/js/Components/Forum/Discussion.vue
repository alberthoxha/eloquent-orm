<template>
    <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
        <div class="p-6 text-gray-900 flex item-center space-x-6">
            <div class="flex-grow">
                <div class="flex items-center space-x-3">
                    <span
                        class="inline-flex item-center rounded-lg bg-gray-100 px-3 py-0.5 text-sm text-gray-600"
                        >{{ discussion.topic.title }}</span
                    >
                    <h1 class="text-lg font-medium">
                        <template v-if="discussion.is_pinned">
                            [Pinned]
                        </template>
                        {{ discussion.title }}
                    </h1>
                </div>
            </div>
            <div>Avatars</div>
        </div>
    </div>
</template>

<script setup>
defineProps({
    discussion: Object,
});
</script>

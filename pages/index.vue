<template>
  <div class="prose mb-12">
    <h1>
      <span class="font-medium">
        <span class="font-bold">科学课</span>
      </span>
    </h1>
  </div>

  <div class="flex flex-row justify-center flex-grow">
    <div class="prose mr-4 p-8 bg-white rounded-md min-w-[20ch] max-w-[30ch] h-[80vh] overflow-auto flex flex-col">
      <h3>章节</h3>
      
      <div
        class="space-y-1 mb-4 flex flex-col"
        v-for="chapter in chapters"
        :key="chapter.slug"
      >
        <h4>{{ chapter.title }}</h4>
        <NuxtLink
          v-for="(lesson, index) in chapter.lessons"
          :key="lesson.slug"
          class="flex flex-row space-x-1 no-underline prose-sm font-normal py-1 px-4 -mx-4"
          :to="lesson.path"
          :class="{
            'text-blue-500':lesson.path === $route.fullPath,
            'text-gray-600': lesson.path !== $route.fullPath
          }"
        >
          <span class="text-gray-500"
            >{{ index + 1 }}.</span
          >
          <span>{{ lesson.title }}</span>
        </NuxtLink>
      </div>
    </div>

    <div class="prose p-12 bg-white rounded-md w-[65ch]">
      <NuxtPage />
    </div>
  </div>
</template>

<script setup>
const { chapters } = useCourse()
</script>

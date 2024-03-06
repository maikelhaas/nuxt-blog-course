<template>
  <article
    class="prose max-w-none dark:prose-invert prose-pre:bg-gray-100 prose-pre:text-gray-700 dark:prose-pre:bg-gray-800 dark:prose-pre:text-gray-300"
  >
    <ContentDoc>
      <template #not-found>
        <h1>Document not found</h1>
      </template>
      <template #default="{ doc }">
        <div class="grid grid-cols-6 gap-16">
          <div :class="{ 'col-span-4': doc.toc, 'col-span-6': !doc.toc }">
            <ContentRenderer :value="doc" />
          </div>
          <div v-if="doc.toc" class="col-span-2">
            <aside class="not-prose sticky top-8">
              <div class="mb-2 font-semibold">Table of Contents:</div>
              <nav><TableOfContents :links="doc.body.toc.links" /></nav>
            </aside>
          </div>
        </div>
      </template>
    </ContentDoc>
  </article>
</template>

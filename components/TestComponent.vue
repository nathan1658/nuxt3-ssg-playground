<template>
    <div>
        {{ post }}
    </div>
</template>

<script setup lang="ts">
// Define params wherever, through `defineProps()`, `useRoute()`, etc.
const { data: post, refresh } = await useAsyncData('post', async () => { 

    // wait for 5 seconds
    await new Promise(resolve => setTimeout(resolve, 5000));

    const url = "https://storage.googleapis.com/hk-swimming.appspot.com/latest.json?1691673650902";
   return   $fetch(url);
} )
// Or instead - useFetch is a convenience wrapper around useAsyncData when you're just performing a simple fetch
</script>
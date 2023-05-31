<template>
    <div class="new-card">
        <h2>{{ article.title }}</h2>
        <p>{{ article.description }}</p>
        <p class="author">Autor: {{ article.author }}</p>
    </div>
</template>

<style scoped>
.new-card {
    margin-bottom: 20px;
    padding: 10px;
    background-color: #a1a3a7;
    color: #FFFFFF;
    border-radius: 4px;
}

.new-card h2 {
    font-size: 18px;
    margin-bottom: 5px;
}

.new-card p {
    font-size: 14px;
    margin-bottom: 5px;
}

.new-card p.author {
    font-style: italic;
}
</style>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props: {
        article: {
            type: Object,
            required: true,
        },
    },
});
</script>
  
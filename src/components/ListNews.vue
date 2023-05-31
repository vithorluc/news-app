<template>
    <div>
        <ul>
            <NewCard v-for="article in articles" :key="1" :article="article" />
        </ul>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import NewCard from './NewCard.vue';

export default defineComponent({
    components: {
        NewCard,
    },
    props: {
        articles: {
            type: Array,
            required: true
        }
    }
});
</script>
  
  
<style scoped>
.list-news {
    margin-bottom: 20px;
}

.list-news-item {
    margin-bottom: 10px;
    padding: 10px;
    background-color: #36393F;
    color: #FFFFFF;
    border-radius: 4px;
}

.list-news-item h2 {
    font-size: 18px;
    margin-bottom: 5px;
}

.list-news-item p {
    font-size: 14px;
    margin-bottom: 5px;
}

.list-news-item p.author {
    font-style: italic;
}
</style>


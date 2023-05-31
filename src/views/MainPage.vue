<template>
    <div class="search-bar">
        <h2>Pesquisar</h2>
        <SearchBar @search="fetchNews" />
    </div>
    <div class="main-page">
        <h1>Notícias</h1>
        <div class="container">
            <div class="left-panel">
                <ListNews :articles="articles" />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ListNews from '../components/ListNews.vue';
import SearchBar from '../components/SearchBar.vue';

export default defineComponent({
    components: {
        ListNews,
        SearchBar,
    },
    data() {
        return {
            articles: [],
        };
    },
    mounted() {
        this.fetchNews({});
    },
    methods: {
        async fetchNews({ keyword = '', category = '' }) {
            const apiKey = '42af1a0eeec24f1bb014baa010a8eae0';
            let url = `https://newsapi.org/v2/top-headlines?country=br&apiKey=${apiKey}`;

            if (keyword) {
                url += `&q=${keyword}`;
            }

            if (category) {
                url += `&category=${category}`;
            }
            const response = await fetch(url);
            const data = await response.json();

            if (data.articles) {
                this.articles = data.articles;
            }
        },
    },
});
</script>

<style scoped>
.search-bar {
    background-color: #f2f2f2;
    padding: 20px;
    border-radius: 8px;
}

.main-page {
    max-width: 960px;
    margin: 0 auto;
    padding: 20px;
}

.container {
    display: flex;
}

.left-panel {
    flex: 1;
}

.right-panel {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.card {
    background-color: #f2f2f2;
    padding: 20px;
    border-radius: 8px;
}
</style>

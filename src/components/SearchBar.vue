<template>
    <div>
        <input type="text" v-model="searchQuery" placeholder="Pesquisar por notícias" />
        <select v-model="selectedCategory">
            <option value="">Todas as categorias</option>
            <option value="business">Negócios</option>
            <option value="entertainment">Entretenimento</option>
            <option value="health">Saúde</option>
            <option value="science">Ciência</option>
            <option value="sports">Esportes</option>
            <option value="technology">Tecnologia</option>
        </select>
        <button @click="search">Pesquisar</button>
    </div>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    data() {
        return {
            searchQuery: '',
            selectedCategory: '',
        };
    },
    methods: {
        search() {
            this.$emit('search', {
                keyword: this.searchQuery,
                category: this.selectedCategory,
            });
        },
    },
});
</script>


<style lang="scss">
.search-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 20px;

    input[type="text"] {
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 4px;
        width: 300px;
        margin-right: 10px;
    }

    select {
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 4px;
        width: 200px;
        margin-right: 10px;
    }

    button {
        padding: 10px 20px;
        background-color: #36393F;
        color: #FFFFFF;
        border: none;
        border-radius: 4px;
        cursor: pointer;
    }
}
</style>
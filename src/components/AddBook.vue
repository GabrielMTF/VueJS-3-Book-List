<script setup>
import Books from './Books.vue';

let newBook = {
    title: "",
    cover: "",
    isRead: false,
    isbn: "",
    author: "",
}

const props = defineProps(['showAddBook'])

</script>

<template>
    <h1>📖 Adicionar Livro</h1>

    <div class="header-btns">
        <button @click="$emit('closeAddBook')" class="btn">
            Fechar x
        </button>
    </div>

    <form class="add-form">

        <div class="form-control">
            <label>Título</label>
            <input required v-model="newBook.title" type="text" name="text" placeholder="Adicione o título" />
        </div>
        <div class="form-control">
            <label>Capa</label>
            <input required v-model="newBook.cover" type="text" name="cover"
                placeholder="Adicione o link da imagem de capa" />
        </div>
        <div class="form-control">
            <label>Autor</label>
            <input v-model="newBook.author" type="text" name="author" placeholder="Adicione o autor" />
        </div>
        <div class="form-control">
            <label>ISBN#</label>
            <input v-model="newBook.isbn" type="text" name="isbn" placeholder="Adicione o ISBN" />
        </div>
        <div class="form-control form-control-check">
            <input v-model="newBook.isRead" type="checkbox" name="readIt" id="readIt" />
            <label for="readIt">Já li o livro</label>
        </div>

        <button @click.prevent="$emit('addBook', newBook)" type="submit" class="btn btn-block">Salvar livro</button>
    </form>
</template>

<script setup></script>
<script setup>
const personagem = defineProps(["name", "status", "especie", "genero", "localizacao_atual","episodio" , "imagem"])

</script>

<template>
    <div class="col-md-4">
        <div class="card p-2 mb-3" >
            <img :src="personagem.imagem" style="border-radius: 5%;" >
            <p class="text-center">Nome: {{ personagem.name }}</p>
            <p class="text-center">Status: {{ personagem.status }}</p>
            <p class="text-center">Espécie: {{ personagem.especie }}</p>
            <p class="text-center">Gênero: {{ personagem.genero }}</p>
            <p class="text-center">Episódios: {{ personagem.episodio.length }}</p>
            <p class="text-center">Localização Atual: {{ personagem.localizacao_atual }}</p>
        </div>
    </div>    
</template>

<style>

</style>
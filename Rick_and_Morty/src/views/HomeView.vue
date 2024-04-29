<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListComponents from '@/components/ListComponents.vue';
let personagens = reactive(ref());


onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
    .then(response => response.json())
    .then(response => {
      personagens.value = response.results
      console.log(personagens)
    })
})
</script>

<template>
  <main>
    <div class="container">
      <div >
        

        <div >
          <div class="card">
            <div class="card-body row">
              <ListComponents v-for="personagem in personagens" 
                :imagem="personagem.image" 
                :name="personagem.name" 
                :status="personagem.status" 
                :especie="personagem.species" 
                :genero="personagem.gender" 
                :episodio="personagem.episode" 
                :localizacao_atual="personagem.location.name" 
                />

            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import Card from "./Card.vue";
//importando o axios -> é uma biblioteca JS para faz requisições HTTP
import axios from "axios";

//importamos o ref -> uma funcionalidade que permite criar variaveis reativas
import { ref } from "vue";

//criar uma variavel reativa que vai receber a lista de imagens da api
const imagens = ref([]);

//função assincrona -> 
 async function carregarImagens(){
  //res -> resposta da API
  // AXIOS pegar os dados GET axios.get()
  //await vc precisa esperar o axios ir buscar as imagens
        const res = await axios.get("https://picsum.photos/v2/list?page=3&limit=30");

        imagens.value = res.data;
        //guardando as imagens da API dentro da variavel imagens
        //
        console.log(res)
  }

carregarImagens();
</script>




<template>
  <h2>Inspire-se</h2>
  <section class="inspire">
    <Card
    v-for="img in imagens"
    :imagem="img.download_url"
    />
  </section>
</template>

<style scoped lang="scss">
.inspire, h2{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 10px;
    margin: 2rem;
}
</style>

<script setup>
import { ref } from 'vue';
defineProps(["imagem"]);
//o que é o defineProps
//é uma função do vue que permite receber dados em comunicação de componentes

const liked = ref(false);
//começa não curtida;
</script>

<template>

    <div class="card">
        <!-- icone do favoritar -->
         <span @click="liked = !liked">
            {{ liked ? "❤️" : "🤍" }}
            <!-- operador ternario, é uma forma simples de criar um if/else -->
             <!-- condição ? se_o_valor_for_verdadeiro : valor_falso -->
         </span>
        <img :src="imagem" alt="Imagem do card">
    </div>
    
</template>

<style scoped lang="scss">
.card{
    //border: solid;
    width: 35vw;

   
    img{
        width: 100%;
        height: 100%;
        border-radius: 10px;
    }

    
}
</style>
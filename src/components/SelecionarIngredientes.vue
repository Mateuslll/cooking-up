<script lang="ts">
import { obterCategorias } from '@/http/index';
    export default {
        data(){
            return{
                categorias: obterCategorias()
            }
        }
    }
</script>

<template>
    <section class="selecionar-ingredientes">
        <h1 class="cabecalho titulo-ingredientes">Ingredientes</h1>

        <p class="parafrafo-lg instrucoes ">
            Selecione abaixo os ingredientes que você quer usar nesta receita:
        </p>
        <ul class="categorias">
            <li v-for="categoria in categorias" :key="categoria.nome" >
                {{ categoria.nome }}
            </li>
        </ul>
        <p class="paragrafo dica">
            *Atenção esperamos que voce tenha em casa sal, pimenta e água.
        </p>
    </section>

</template>


<style scoped>


</style>
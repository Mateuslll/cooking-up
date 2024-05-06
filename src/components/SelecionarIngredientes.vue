<script lang="ts">
import { obterCategorias } from '@/http/index';
import type ICategoria from '@/interfaces/ICategoria';
import CardCategoria from './CardCategoria.vue';
export default {
    data() {
        return {
            categorias: [] as ICategoria[]
        };
    },
    //metodo de ciclo de vida executado depois que o data estive definido
    async created() {
        this.categorias = await obterCategorias();
    },
    components: { CardCategoria }
}
</script>

<template>
    <section class="selecionar-ingredientes">
        <h1 class="cabecalho titulo-ingredientes">Ingredientes</h1>

        <p class="parafrafo-lg instrucoes ">
            Selecione abaixo os ingredientes que você quer usar nesta receita:
        </p>
        <ul class="categorias">
            <li v-for="categoria in categorias" :key="categoria.nome">
                <CardCategoria :categoria="categoria"/>
            </li>
        </ul>
        <p class="paragrafo dica">
            *Atenção esperamos que voce tenha em casa sal, pimenta e água.
        </p>
    </section>
</template>


<style scoped></style>
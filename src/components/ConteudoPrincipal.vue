
<script setup lang="ts">
/*Composition Api */
    [
      {
        "nome": "Laticínios e Ovos",
        "ingredientes": ["Ovos", "Queijo", "Leite", "Manteiga", "Creme de Leite", "Iogurte", "Leite Condensado", "Sorvete"],
        "rotulo": "laticinios_e_ovos"
      },
      {
        "nome": "Farinhas e Fermentos",
        "ingredientes": ["Farinha de trigo", "Polvilho", "Farinha de rosca", "Canjica", "Farinha de mandioca", "Fubá", "Linhaça", "Fermento químico"],
        "rotulo": "farinhas_e_fermentos"
      }
    ]
  const listaIngredientes: string[] = ['Alho', 'Manteiga', 'Orégano','Pão','Tomilho', 'Limão']
 </script>

 
<template>
    <main class="conteudo-principal">
        <section>
            <span class="subtitulo-lg sua-lista-texto">
                Sua lista:
            </span>
            <ul v-if="listaIngredientes.length != 0" class="ingredientes-sua-lista">
                  <li v-for="ingrediente in listaIngredientes" class="ingrediente" v-bind:key="ingrediente">
                    {{ ingrediente }}
                </li>
              </ul>
              <p v-else class="paragrafo lista-vazia">
                <img src="../assets/images/icones/lista-vazia.svg" alt="Ícone de pesquisa">
                Sua lista está vazia, selecione os ingredientes para inciar
              </p>   
        </section>
    </main>
  </template>


<style scoped>
.conteudo-principal {
  padding: 6.5rem 7.5rem;
  border-radius: 3.75rem 3.75rem 0rem 0rem;
  background: var(--creme, #FFFAF3);
  color: var(--cinza, #444);

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5rem;
}

.sua-lista-texto {
  color: var(--coral, #F0633C);
  display: block;
  text-align: center;
  margin-bottom: 1.5rem;
}

.ingredientes-sua-lista {
  display: flex;
  justify-content: center;
  gap: 1rem 1.5rem;
  flex-wrap: wrap;
}

.ingrediente {
  display: inline-block;
  border-radius: 0.5rem;
  min-width: 4.25rem;
  padding: 0.5rem;
  text-align: center;
    transition: 0.2s;
    color: var(--creme, #FFFAF3);
  background: var(--coral, #F0633C);
  font-weight: 700;
}

.lista-vazia {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 0.25rem;

  color: var(--coral, #F0633C);
  text-align: center;
}

@media only screen and (max-width: 1300px) {
  .conteudo-principal {
    padding: 5rem 3.75rem;
    gap: 3.5rem;
  }
}

@media only screen and (max-width: 767px) {
  .conteudo-principal {
    padding: 4rem 1.5rem;
    gap: 4rem;
  }
}
</style>

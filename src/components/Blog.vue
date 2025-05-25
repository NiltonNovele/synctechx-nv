<template>
  <div class="min-h-screen bg-black text-white py-12 px-4 sm:px-8">
    <h1 v-if="!selectedPost" class="text-4xl font-bold text-center mb-12">
      Blog
    </h1>

    <!-- Lista de Artigos -->
    <div v-if="!selectedPost" class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
      <div
        v-for="post in blogPosts"
        :key="post.id"
        class="bg-zinc-900 rounded-2xl overflow-hidden shadow-lg hover:shadow-xl transition"
      >
        <img
          :src="post.image"
          alt="Imagem do artigo"
          class="h-48 w-full object-cover"
        />
        <div class="p-6">
          <div
            class="flex items-center justify-between text-sm text-gray-400 mb-2"
          >
            <span>{{ post.author }}</span>
            <span>{{ post.date }}</span>
          </div>
          <h2 class="text-2xl font-semibold text-blue-400 mb-3">
            {{ post.title }}
          </h2>
          <p class="text-gray-300 mb-4">{{ post.excerpt }}</p>
          <button
            @click="selectedPost = post"
            class="text-blue-400 hover:underline"
          >
            Ler mais
          </button>
        </div>
      </div>
    </div>

    <!-- Artigo Completo -->
    <div v-else class="max-w-3xl mx-auto">
      <button
        @click="selectedPost = null"
        class="mb-6 text-sm text-blue-400 hover:underline"
      >
        ← Voltar ao blog
      </button>
      <h1 class="text-4xl font-bold text-blue-400 mb-4">
        {{ selectedPost.title }}
      </h1>
      <p class="text-sm text-gray-400 mb-4">
        Por {{ selectedPost.author }} • {{ selectedPost.date }}
      </p>
      <img
        :src="selectedPost.image"
        alt="Imagem do artigo"
        class="rounded-xl mb-8 w-full h-56 object-cover"
      />
      <p class="text-gray-200 leading-relaxed whitespace-pre-line">
        {{ selectedPost.full }}
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const selectedPost = ref(null);

const blogPosts = [
  //   {
  //     id: 1,
  //     title: "Why Vue 3 is Awesome",
  //     date: "May 25, 2025",
  //     author: "Nilton Novele",
  //     excerpt:
  //       "Vue 3 introduces Composition API, better performance, and more flexibility...",
  //     full: `Vue 3 introduces the Composition API, which allows you to write more flexible and reusable code. It also improves performance and tree-shaking for smaller bundle sizes. Vue 3 supports better TypeScript integration and includes new features like <Teleport>, <Suspense>, and Fragment support.\n\nThis means your Vue apps can now be faster, leaner, and easier to maintain — a big win for developers building complex interfaces.`,
  //     image: "https://source.unsplash.com/600x400/?vue,code",
  //   },
  {
    id: 4,
    title: "Como validar a sua ideia de startup rapidamente",
    date: "25 de maio de 2025",
    author: "Henzel Tibana",
    excerpt:
      "Validar a sua ideia de startup é essencial para evitar desperdício de tempo e recursos. Aprenda métodos práticos para testar o seu conceito rapidamente.",
    full: `Validar a sua ideia de startup é um passo crucial antes de investir tempo e dinheiro no desenvolvimento completo do produto. Muitas startups falham porque nunca confirmaram se existe realmente uma necessidade para o que estão a criar.

Aqui ficam algumas dicas para validar a sua ideia rapidamente:

1. Converse com potenciais clientes.
Fale com pessoas do seu público-alvo para perceber se têm o problema que pretende resolver e se estariam dispostas a pagar pela solução.

2. Crie um MVP simples.
Desenvolva uma versão mínima do produto com as funcionalidades essenciais para que os utilizadores possam testar.

3. Teste anúncios.
Use plataformas como Facebook ou Google Ads para promover a sua ideia e medir o interesse do público.

4. Utilize landing pages.
Crie uma página simples que explique a sua proposta de valor e inclua um call-to-action, como uma inscrição para uma lista de espera.

5. Colete feedback e itere.
Ouça o que os utilizadores dizem, melhore o seu produto e volte a testar.

Validar cedo permite ajustar o rumo, poupar recursos e aumentar as hipóteses de sucesso da sua startup.

Lembre-se: o mais importante é resolver um problema real com uma solução que as pessoas realmente querem usar.`,

    image: "/blog2.jpg",
  },

  {
    id: 3,
    title: "Ter ideias...",
    date: "18 de maio de 2025",
    author: "Henzel Tibana",
    excerpt:
      "Grandes ideias são empolgantes — mas também pesadas. Eis o que fazer quando estás a carregar demasiada visão.",
    full: `Grandes ideias surgem como um relâmpago — rápidas, poderosas, eletrizantes. Podes estar a caminho de casa, a tomar banho, ou simplesmente deitado acordado às 2 da manhã, e de repente: bum — algo se liga. Vês uma nova solução, uma forma de mudar as coisas, uma visão que faz o teu coração disparar. É como se estivesses a segurar o plano de algo que o mundo precisa. E naquele momento, é a coisa mais emocionante do mundo.

Mas aqui está a parte que as pessoas não falam o suficiente:
Grandes ideias também são pesadas.

Pesam-te no peito. Seguem-te como uma sombra. Mantêm-te acordado porque estás a pensar:
“Como é que começo sequer?”
“E se outra pessoa fizer isto primeiro?”
“E se eu não for bom o suficiente para concretizar?”

Já senti esse peso mais vezes do que consigo contar. Quando és jovem, ambicioso e com fome de vencer, a pressão para executar as tuas ideias pode ser sufocante — especialmente se sentes que o tempo, o dinheiro e o apoio estão todos contra ti.

E a internet não ajuda. Estamos constantemente bombardeados com destaques — sucessos do dia para a noite, milionários com 19 anos, startups virais — e isso cria a ilusão de que, se não estás a construir rápido, a lançar já ou a crescer instantaneamente, já estás atrasado. Mas isso é mentira.

Com o tempo, aprendi a deixar de tratar as minhas ideias como bombas relógio e a começar a tratá-las como sementes. Algumas ideias devem brotar imediatamente. Outras precisam de tempo — tempo para crescer, evoluir e, honestamente, tempo para que te tornes na pessoa capaz de as carregar de forma adequada.

Aqui está o que me ajudou a manter a sanidade enquanto carregava grandes ideias:

1. Começa pequeno.
Por maior que seja a tua visão, não precisa de um começo dramático. Um esboço rápido, uma nota de voz de 10 minutos, um protótipo básico — isso é suficiente. Não caias na armadilha de pensar que não é “real” até estar perfeito. Apenas começa.

2. Escreve tudo.
Regista tudo. Cada ideia, nome, esboço, pensamento tardio. Não é só para a memória — é uma forma de respeito. Quando escreves algo, estás a mostrar à tua ideia que ela importa. Alguns dos meus melhores trabalhos começaram como notas confusas no meu telemóvel.

3. Fala com as pessoas certas.
Nem todos vão perceber a tua visão — e está tudo bem. Evita a malta do hype e os “mata-sonhos”. Encontra pessoas ponderadas, curiosas, que desafiem o teu pensamento mas que também acreditem em ti o suficiente para dizer: “continua”.

4. Desliga-te do resultado.
Esta foi a mais difícil para mim. Tu não controlas quando a tua ideia vai ser aceite pelo mundo. Por vezes, não vai — não agora, nem nunca. Mas isso não significa que tenha sido uma perda de tempo. Cada grande ideia ensina-te algo. Às vezes, ensina-te o que precisas de ser primeiro.

Grandes ideias são bonitas. São também um peso.
Mas se aprenderes a carregá-las com paciência, disciplina e honestidade, elas vão moldar-te mais do que qualquer outra coisa.

Por isso, se estás a ler isto e tens uma ideia pesada no peito — não tenhas pressa. Não entres em pânico. Não desistas.
Segue em frente.
Mantém os pés no chão.
Constrói devagar.

O mundo precisa do que estás a sonhar — mas, mais do que isso, precisa de ti saudável, focado e inteiro para o conseguir entregar.

Grandes ideias não requerem um grande ego.
Requerem um grande coração.

E se tens isso — já estás a caminho.`,
    image: "/blog1.jpg",
  },
];
</script>

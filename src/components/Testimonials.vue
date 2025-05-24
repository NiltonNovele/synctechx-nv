<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";

import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";

import { Star } from "lucide-vue-next";

interface ReviewProps {
  image: string;
  name: string;
  userName: string;
  comment: string;
  rating: number;
}

const reviewList: ReviewProps[] = [
  {
    image: "https://github.com/shadcn.png",
    name: "Carlos Mucavele",
    userName: "Gestor de Produto na MaputoTech",
    comment:
      "A nossa equipa conseguiu lançar uma nova funcionalidade 2x mais rápido graças à integração fácil e componentes reutilizáveis deste sistema.",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Lídia Gimo",
    userName: "Analista de Dados na Beira Digital",
    comment:
      "Fiquei surpreendida com a facilidade de personalização e a rapidez de desenvolvimento. Excelente para startups locais!",
    rating: 4.9,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Edson Júnior",
    userName: "Engenheiro de Software na NampulaSoft",
    comment:
      "É raro encontrar uma solução tão bem pensada e adaptável às nossas necessidades aqui em Moçambique.",
    rating: 4.8,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Vanessa Chissano",
    userName: "Fundadora da Startup Kulima",
    comment:
      "Este template foi essencial para apresentar a nossa ideia de forma profissional e rápida. Recebemos ótimos feedbacks!",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Henrique Tivane",
    userName: "CTO da InnoMoz",
    comment:
      "Nosso time técnico ficou impressionado com a estrutura limpa e o suporte a dark mode nativo. Muito útil no nosso dia a dia.",
    rating: 4.9,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Tatiana Machava",
    userName: "UX Designer na DevMaputo",
    comment:
      "A experiência do utilizador ficou muito mais fluída e moderna. Os componentes são muito intuitivos!",
    rating: 5.0,
  },
];
</script>

<template>
  <section id="testemunhos" class="container py-24 sm:py-32">
    <div class="text-center mb-8">
      <h2 class="text-lg text-blue-600 text-center mb-2 tracking-wider">
        Testemunhos
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
        Veja o que dizem os nossos clientes em Moçambique
      </h2>
    </div>

    <Carousel
      :opts="{ align: 'start' }"
      class="relative w-[80%] sm:w-[90%] lg:max-w-screen-xl mx-auto"
    >
      <CarouselContent>
        <CarouselItem
          v-for="review in reviewList"
          :key="review.name"
          class="md:basis-1/2 lg:basis-1/3"
        >
          <Card class="bg-muted/50 dark:bg-card">
            <CardContent class="pt-6 pb-0">
              <div class="flex gap-1 pb-6">
                <Star
                  v-for="i in 5"
                  :key="i"
                  class="size-4 fill-blue-600 text-blue-600"
                />
              </div>

              “{{ review.comment }}”
            </CardContent>

            <CardHeader>
              <div class="flex flex-row items-center gap-4">
                <Avatar>
                  <AvatarImage :src="review.image" :alt="review.name" />
                  <AvatarFallback>{{ review.name[0] }}</AvatarFallback>
                </Avatar>

                <div class="flex flex-col">
                  <CardTitle class="text-lg">{{ review.name }}</CardTitle>
                  <CardDescription>{{ review.userName }}</CardDescription>
                </div>
              </div>
            </CardHeader>
          </Card>
        </CarouselItem>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </Carousel>
  </section>
</template>

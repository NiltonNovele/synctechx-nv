<script setup lang="ts">
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { ExternalLink } from "lucide-vue-next";

interface Project {
  title: string;
  description: string;
  imageUrl: string;
  tags: string[];
  link: string;
}

const projects: Project[] = [
  {
    title: "Bookit CPT",
    description:
      "Descubra e agende horários em salões, clínicas, restaurantes e muito mais — tudo em um só lugar ou pelo WhatsApp. Rápido. Fácil. Confiável.",
    imageUrl: "/bookit.png",
    tags: ["Next.js", "TypeScript", "MongoDB", "TailwindCSS", "OpenAI"],
    link: "https://bookit.niltonnovele.com",
  },
  {
    title: "CarePulse",
    description:
      "Plataforma para melhor rastreio de pacientes e receitas medicas.",
    imageUrl: "/carepulse.png",
    tags: ["REST API", "Express", "PostgreSQL"],
    link: "https://carepulse.synctechx.com",
  },
  {
    title: "AMECC",
    description:
      "Plataforma para a Associação Moçambicana de Estudantes a Cidade do Cabo com diversas funcionalidades.",
    imageUrl: "/amecc.png",
    tags: ["TailwindCSS", "Next.Js", "Express"],
    link: "https://amecc.vercel.app",
  },
];
</script>

<template>
  <section class="container py-24 sm:py-32">
    <h2 class="text-lg text-blue-600 text-center mb-2 tracking-wider">
      Projetos
    </h2>
    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Veja alguns dos nossos trabalhos
    </h2>
    <h3
      class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground pb-14"
    >
      Aplicações modernas desenvolvidas com tecnologias de ponta para empresas e
      utilizadores.
    </h3>

    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
      <Card
        v-for="{ title, description, imageUrl, tags, link } in projects"
        :key="title"
        class="transition-all duration-300 transform hover:-translate-y-2 hover:shadow-xl hover:border-blue-600 border border-blue-200 bg-background rounded-2xl overflow-hidden"
      >
        <CardHeader class="p-0">
          <div class="overflow-hidden rounded-t-2xl">
            <img
              :src="imageUrl"
              :alt="title"
              class="h-48 w-full object-cover transition-transform duration-300 hover:scale-105"
            />
          </div>
          <div class="p-6">
            <CardTitle class="text-xl mb-2">{{ title }}</CardTitle>
            <CardDescription class="text-base">
              {{ description }}
            </CardDescription>
          </div>
        </CardHeader>

        <CardContent class="px-6 flex flex-wrap gap-2 py-2">
          <span
            v-for="tag in tags"
            :key="tag"
            class="text-xs bg-blue-50 text-blue-700 px-2 py-1 rounded-full font-medium"
          >
            {{ tag }}
          </span>
        </CardContent>

        <CardFooter class="px-6 pb-6">
          <a
            :href="link"
            target="_blank"
            rel="noopener noreferrer"
            class="w-full"
          >
            <Button
              class="w-full flex items-center justify-center gap-2 bg-blue-600 text-white hover:bg-blue-700 transition-colors duration-300"
            >
              Ver Projeto <ExternalLink class="w-4 h-4" />
            </Button>
          </a>
        </CardFooter>
      </Card>
    </div>
    <br />
    <div class="flex justify-center mt-6">
      <Button
        class="px-4 py-2 text-sm font-medium bg-blue-600 text-white hover:bg-blue-700 transition-colors duration-300 rounded-lg inline-flex items-center gap-1"
      >
        Ver Mais Projetos
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="w-4 h-4"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M9 5l7 7-7 7"
          />
        </svg>
      </Button>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";

interface HowItWorksProps {
  badgeTitle: string;
  title: string;
  description: string;
  image: string;
}

const HowItWorksList: HowItWorksProps[] = [
  {
    badgeTitle: "Contribuir",
    title: "Transforme a sua ideia em impacto real",
    description:
      "Acreditamos no poder das ideias locais. Participe com sugestões, soluções ou código e ajude-nos a criar tecnologia relevante para Moçambique.",
    image: "/roboto.png",
  },
  {
    badgeTitle: "Descobrir",
    title: "Explore soluções criadas para a nossa realidade",
    description:
      "A nossa plataforma permite que você descubra produtos e serviços desenvolvidos com foco nas necessidades das comunidades moçambicanas.",
    image: "/runner.png",
  },
  {
    badgeTitle: "Inovar",
    title: "Tecnologia que resolve desafios reais",
    description:
      "Combinamos talento local com inovação global para criar ferramentas que impulsionam a educação, saúde, e economia digital no país.",
    image: "/pacheco.png",
  },
  {
    badgeTitle: "Colaborar",
    title: "Juntos, somos mais fortes",
    description:
      "Trabalhamos em parceria com startups, instituições e indivíduos para ampliar o alcance e impacto das nossas soluções.",
    image: "/gamestation.png",
  },
];
</script>

<template>
  <section id="features" class="container py-24 sm:py-32">
    <div class="text-center mb-8">
      <h2 class="text-lg text-blue-600 text-center mb-2 tracking-wider">
        Como Funciona
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Passo-a-Passo do Nosso Processo
      </h2>
    </div>

    <div class="lg:w-[80%] mx-auto relative">
      <div
        v-for="(
          { badgeTitle, title, description, image }, index
        ) in HowItWorksList"
        :key="title"
        :class="[
          'flex mb-8 items-center',
          { ' flex-row-reverse': index % 2 !== 0 },
        ]"
      >
        <Card class="h-full bg-transparent border-0 shadow-none">
          <CardHeader>
            <div class="pb-4">
              <Badge class="bg-blue-600 text-white">{{ badgeTitle }}</Badge>
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground w-[80%]">
            {{ description }}
          </CardContent>
        </Card>

        <img
          :src="image"
          :alt="`Image describing ${title} `"
          className="w-[150px]  md:w-[250px] lg:w-[300px] mx-auto -scale-x-100 "
        />
        <div
          :class="[
            '-z-10 absolute right-0 w-44 h-72  lg:w-64 lg:h-80 rounded-full bg-blue-600/15 dark:bg-blue-600/10 blur-3xl',
            {
              'left-0': index % 2 !== 0,
            },
          ]"
        ></div>
      </div>
    </div>
  </section>
</template>

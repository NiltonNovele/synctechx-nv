<script setup lang="ts">
import {
  Card,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import { Badge } from "@/components/ui/badge";

enum ProService {
  YES = 1,
  NO = 0,
}

interface ServiceProps {
  title: string;
  pro: ProService;
  description: string;
}

const serviceList: ServiceProps[] = [
  {
    title: "Desenvolvimento de Software Personalizado",
    description:
      "Criamos soluções de software sob medida para atender às necessidades específicas do seu negócio.",
    pro: ProService.NO,
  },
  {
    title: "Desenvolvimento e Manutenção de Websites",
    description:
      "Projetamos websites modernos, responsivos e otimizados, com suporte contínuo para garantir o melhor desempenho.",
    pro: ProService.NO,
  },
  {
    title: "Integração de Sistemas",
    description:
      "Conectamos diferentes plataformas e sistemas para melhorar a eficiência e a automação dos seus processos.",
    pro: ProService.NO,
  },
  {
    title: "Suporte e Manutenção Técnica PRO",
    description:
      "Serviço avançado de suporte técnico contínuo para garantir que as suas soluções tecnológicas funcionem sempre na perfeição.",
    pro: ProService.YES,
  },
];
</script>

<template>
  <section id="services" class="container py-24 sm:py-32">
    <h2 class="text-lg text-blue-600 text-center mb-2 tracking-wider">
      Serviços
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Faça o Seu Negócio Crescer com Tecnologia
    </h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Desenvolvimento, manutenção e suporte para que o seu negócio esteja sempre
      à frente.
    </h3>

    <div
      class="grid sm:grid-cols-2 lg:grid-cols-2 gap-4 w-full lg:w-[60%] mx-auto"
    >
      <div v-for="{ title, description, pro } in serviceList" :key="title">
        <Card class="bg-muted/60 dark:bg-card h-full relative">
          <CardHeader>
            <CardTitle>{{ title }}</CardTitle>
            <CardDescription>{{ description }}</CardDescription>
          </CardHeader>
          <Badge
            v-if="pro === ProService.YES"
            variant="secondary"
            class="absolute -top-2 -right-3"
            >PRO</Badge
          >
        </Card>
      </div>
    </div>
  </section>
</template>

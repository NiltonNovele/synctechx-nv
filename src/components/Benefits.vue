<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Sparkle,
  Tag,
  Paintbrush,
  Blocks,
  LineChart,
  Wallet,
} from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "sparkle",
    title: "Visão",
    description:
      "Ser uma referência inovadora na criação e manutenção de soluções tecnológicas que transformam negócios.",
  },
  {
    icon: "paintbrush",
    title: "Missão",
    description:
      "Desenvolver software de alta qualidade que potencia o crescimento das empresas, com foco em tecnologia de ponta e atendimento personalizado.",
  },
  {
    icon: "blocks",
    title: "Valores",
    description:
      "Inovação, transparência, compromisso e excelência técnica são a base do nosso trabalho diário.",
  },
  {
    icon: "tag",
    title: "Quem Somos",
    description:
      "Uma equipa jovem e dinâmica, apaixonada por tecnologia e dedicada a criar soluções digitais eficientes e escaláveis.",
  },
];

const iconMap: Record<
  string,
  | typeof Sparkle
  | typeof Tag
  | typeof Paintbrush
  | typeof Blocks
  | typeof LineChart
  | typeof Wallet
> = {
  sparkle: Sparkle,
  tag: Tag,
  paintbrush: Paintbrush,
  blocks: Blocks,
  lineChart: LineChart,
  wallet: Wallet,
};
</script>

<template>
  <section id="benefits" class="container py-24 sm:py-32">
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>
        <h2 class="text-lg text-blue-600 mb-2 tracking-wider">Quem Somos</h2>

        <h2 class="text-3xl md:text-4xl font-bold mb-4">A Nossa Essência</h2>
        <p class="text-xl text-muted-foreground mb-8">
          Somos uma equipa jovem e apaixonada por tecnologia, dedicada a
          transformar ideias em soluções digitais que impulsionam o seu negócio.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-4 w-full">
        <Card
          v-for="({ icon, title, description }, index) in benefitList"
          :key="title"
          class="bg-muted/50 dark:bg-card hover:bg-background dark:hover:bg-background transition-all delay-75 group/number"
        >
          <CardHeader>
            <div class="flex justify-between">
              <component
                class="size-8 mb-6 text-blue-600"
                :is="iconMap[icon]"
              />

              <span
                class="text-5xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30"
                >0{{ index + 1 }}</span
              >
            </div>

            <CardTitle>{{ title }}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

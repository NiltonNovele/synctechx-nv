<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Paintbrush,
  MessageCircle,
  TabletSmartphone,
  BadgeCheck,
  Goal,
  PictureInPicture,
  MousePointerClick,
  Newspaper,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "tabletSmartphone",
    title: "Design Responsivo",
    description:
      "Garantimos que os seus websites e aplicações funcionem perfeitamente em qualquer dispositivo, do telemóvel ao desktop.",
  },
  {
    icon: "badgeCheck",
    title: "Qualidade Garantida",
    description:
      "Priorizamos a qualidade e a robustez dos nossos sistemas para assegurar a satisfação e confiança dos nossos clientes.",
  },
  {
    icon: "goal",
    title: "Soluções Personalizadas",
    description:
      "Desenvolvemos software adaptado às necessidades específicas do seu negócio, focando os seus objetivos principais.",
  },
  {
    icon: "pictureInPicture",
    title: "Interface Intuitiva",
    description:
      "Criamos interfaces claras e fáceis de usar para melhorar a experiência do utilizador e aumentar a produtividade.",
  },
  {
    icon: "mousePointerClick",
    title: "Ações Claras",
    description:
      "Definimos chamadas à ação eficazes que guiam os seus utilizadores para os objetivos desejados.",
  },
  {
    icon: "newspaper",
    title: "Comunicação Transparente",
    description:
      "Mantemos os nossos clientes informados em todas as etapas do projeto, com total transparência e colaboração.",
  },
];

const iconMap: Record<
  string,
  | typeof TabletSmartphone
  | typeof BadgeCheck
  | typeof Goal
  | typeof PictureInPicture
  | typeof Paintbrush
  | typeof MousePointerClick
  | typeof MessageCircle
  | typeof Newspaper
> = {
  tabletSmartphone: TabletSmartphone,
  badgeCheck: BadgeCheck,
  goal: Goal,
  pictureInPicture: PictureInPicture,
  paintbrush: Paintbrush,
  mousePointerClick: MousePointerClick,
  messageCircle: MessageCircle,
  newspaper: Newspaper,
};
</script>

<template>
  <section id="features" class="container py-24 sm:py-32">
    <h2 class="text-lg text-blue-600 text-center mb-2 tracking-wider">
      Funcionalidades
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      O Que Nos Torna Diferentes
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Desenvolvemos e mantemos soluções tecnológicas inovadoras para impulsionar
      o crescimento do seu negócio.
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
      <div v-for="{ icon, title, description } in featureList" :key="title">
        <Card class="h-full bg-background border-0 shadow-none">
          <CardHeader class="flex flex-col justify-center items-center">
            <div
              class="bg-blue-600/20 p-2 rounded-full ring-8 ring-blue-600/10 mb-4"
            >
              <component :is="iconMap[icon]" class="size-6 text-blue-600" />
            </div>

            <CardTitle class="text-center">
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground text-center">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

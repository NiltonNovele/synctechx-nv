<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";

interface FAQProps {
  question: string;
  answer: string;
  value: string;
}

const FAQList: FAQProps[] = [
  {
    question: "Quais serviços a synctechX oferece?",
    answer:
      "Desenvolvimento, Manutenção e consultoria de softwares, Aplicações Web e mobile; Atividades de consultoria em informática, gestão e exploração de equipamento informático; Segurança cibernética e testes de penetração; Inteligência artificial e automação; Soluções para Blockchain & Fintech;",
    value: "item-1",
  },
  {
    question:
      "A Synctechx oferece treinamento para uso dos softwares desenvolvidos?",
    answer:
      "Sim, a Synctechx oferece treinamento completo para garantir que sua equipe saiba como utilizar os softwares desenvolvidos de maneira eficiente. Além disso, oferecemos manutenção contínua, que inclui a resolução de bugs e ajustes conforme necessário, de acordo com os termos estabelecidos no contrato. Nosso objetivo é garantir que nossos clientes tenham a melhor experiência possível com nossas soluções.",
    value: "item-2",
  },
  {
    question: "Os softwares desenvolvidos pela Synctechx são iguais?.",
    answer:
      "Não, cada software desenvolvido pela Synctechx é único. A empresa escuta atentamente as necessidades de cada cliente e cria soluções personalizadas Atendendo de forma precisa aos requisitos específicos de cada um.",
    value: "item-3",
  },
  {
    question: "Como faco para contactar a SyncTechX?",
    answer:
      "Através do e-mail: contacto@synctechx.com; Através do número (+258) 84 752-9665; Deixe-nos uma mensagem com a sua preocupação no formulário abaixo! A equipe da Synctech leva de 5 a 20 horas para responder a qualquer inquérito.",
    value: "item-4",
  },
  {
    question: "Sou um jovem estudante, como posso fazer parte da equipa?",
    answer:
      "Altamente! Envia-nos uma mensagem com o teu cv e estaremos ansiosos por te receber.",
    value: "item-5",
  },
];
</script>

<template>
  <section id="faq" class="container md:w-[700px] py-24 sm:py-32">
    <div class="text-center mb-8">
      <h2 class="text-lg text-blue-400 text-center mb-2 tracking-wider">
        FAQS
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Common Questions
      </h2>
    </div>

    <Accordion type="single" collapsible class="AccordionRoot">
      <AccordionItem
        v-for="{ question, answer, value } in FAQList"
        :key="value"
        :value="value"
      >
        <AccordionTrigger class="text-left"> {{ question }} </AccordionTrigger>

        <AccordionContent>{{ answer }}</AccordionContent>
      </AccordionItem>
    </Accordion>

    <h3 class="font-medium mt-4">
      Ainda tem dúvidas?
      <a href="#" class="text-muted-foreground">
        <a href="#" class="underline">Contate-nos</a>
      </a>
    </h3>
  </section>
</template>

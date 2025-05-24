<script setup lang="ts">
import { useColorMode } from "@vueuse/core";
const mode = useColorMode();

import { Badge } from "@/components/ui/badge";
import { Button } from "@/components/ui/button";
import { ArrowRight } from "lucide-vue-next";
</script>

<template>
  <section class="container">
    <div
      class="grid place-items-center lg:max-w-screen-xl gap-8 mx-auto py-20 md:py-32"
    >
      <div class="text-center space-y-8">
        <Badge variant="outline" class="text-sm py-2 text-blue-600">
          <span class="mr-2 text-blue-600">
            <Badge>Novidade</Badge>
          </span>
          <span>Nova versão do nosso website disponível!</span>
        </Badge>

        <div
          class="max-w-screen-md mx-auto text-center text-5xl md:text-6xl font-bold"
        >
          <h1>
            Potencie o seu negócio com
            <span
              class="text-transparent bg-gradient-to-r from-[#3B82F6] to-blue-600 bg-clip-text"
              >Tecnologia de Ponta
            </span>
          </h1>
        </div>

        <p class="max-w-screen-sm mx-auto text-xl text-muted-foreground">
          Somos uma equipa jovem e dedicada ao desenvolvimento e manutenção de
          software, websites e soluções digitais personalizadas para o seu
          sucesso.
        </p>

        <div class="space-y-4 md:space-y-0 md:space-x-4">
          <Button
            class="w-5/6 md:w-1/4 font-bold group/arrow bg-blue-600 hover:bg-blue-700"
          >
            Começar Agora
            <ArrowRight
              class="size-5 ml-2 group-hover/arrow:translate-x-1 transition-transform"
            />
          </Button>

          <Button as-child variant="secondary" class="w-5/6 md:w-1/4 font-bold">
            <a
              href="https://www.linkedin.com/company/synctechx/"
              target="_blank"
              >LinkedIn</a
            >
          </Button>
        </div>
      </div>

      <div class="relative group mt-14">
        <!-- sombra do gradiente -->
        <div
          class="absolute -top-6 right-12 w-[90%] h-12 lg:h-[80%] bg-blue-600/50 blur-3xl rounded-full img-shadow-animation"
        ></div>

        <img
          class="w-full md:w-[1200px] mx-auto rounded-lg relative leading-none flex items-center border border-t-2 border-t-blue-400/30 img-border-animation"
          :src="
            mode == 'light' ? '/hero-image-light.png' : '/hero-image-dark.png'
          "
          alt="Dashboard da nossa startup tecnológica"
        />

        <!-- efeito gradiente na imagem -->
        <div
          class="absolute bottom-0 left-0 w-full h-20 md:h-28 bg-gradient-to-b from-background/0 via-background/50 to-background rounded-lg"
        ></div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.img-shadow-animation {
  animation-name: img-shadow-animation;
  animation-iteration-count: infinite;
  animation-duration: 2s;
  animation-timing-function: linear;
  animation-direction: alternate;
}

.img-border-animation {
  animation-name: img-border-animation;
  animation-iteration-count: infinite;
  animation-duration: 2s;
  animation-timing-function: linear;
  animation-direction: alternate;
}

@keyframes img-shadow-animation {
  from {
    opacity: 0.5;
    transform: translateY(30px);
  }

  to {
    opacity: 1;
    transform: translateY(0px);
  }
}
@keyframes img-border-animation {
  from {
    border-top-color: rgba(59, 130, 246, 0.1); /* blue-500/10 */
  }

  to {
    border-top-color: rgba(59, 130, 246, 0.6); /* blue-500/60 */
  }
}
</style>

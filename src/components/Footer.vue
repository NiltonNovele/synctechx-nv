<script setup lang="ts">
import Separator from "./ui/separator/Separator.vue";
</script>

<template>
  <footer id="footer" class="container py-24 pb-16 sm:py-32 sm:pb-24">
    <div class="p-10 bg-muted/50 dark:bg-card border rounded-2xl">
      <!-- Grelha de layout -->
      <div
        class="grid grid-cols-2 md:grid-cols-4 xl:grid-cols-6 gap-x-12 gap-y-8"
      >
        <!-- Logótipo -->
        <div class="col-span-full xl:col-span-2">
          <a href="#" class="flex font-bold items-center">
            <img
              src="/logo-nv (1).png"
              alt="Logótipo SyncTechX"
              class="w-9 h-9 mr-2 rounded-lg border"
            />
            <h3 class="text-2xl">SyncTechX</h3>
          </a>
        </div>

        <!-- Equipa -->
        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Equipa</h3>
          <a
            href="https://niltonnovele.com"
            class="opacity-60 hover:opacity-100"
          >
            Nilton Novele
          </a>
          <a
            href="https://www.linkedin.com/in/henzel-tibana-a07068211/"
            class="opacity-60 hover:opacity-100"
          >
            Henzel Tibana
          </a>
          <a href="#" class="opacity-60 hover:opacity-100">Synctechx.com</a>
        </div>

        <!-- Plataformas -->
        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Plataformas</h3>
          <a href="#" class="opacity-60 hover:opacity-100">iOS</a>
          <a href="#" class="opacity-60 hover:opacity-100">Android</a>
          <a href="#" class="opacity-60 hover:opacity-100">Web</a>
        </div>

        <!-- Ajuda -->
        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Ajuda</h3>
          <a href="#" class="opacity-60 hover:opacity-100">Contacte-nos</a>
          <a href="#" class="opacity-60 hover:opacity-100"
            >Perguntas Frequentes</a
          >
          <a href="#" class="opacity-60 hover:opacity-100">Feedback</a>
        </div>

        <!-- Redes Sociais -->
        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Redes Sociais</h3>
          <a
            href="https://www.linkedin.com/company/synctechx/"
            class="opacity-60 hover:opacity-100"
          >
            LinkedIn
          </a>
          <a
            href="https://www.instagram.com/synctechxmz/"
            class="opacity-60 hover:opacity-100"
          >
            Instagram
          </a>
          <a
            href="https://www.facebook.com/profile.php?id=61574813828863"
            class="opacity-60 hover:opacity-100"
          >
            Facebook
          </a>
        </div>
      </div>

      <!-- Separador e direitos -->
      <Separator class="my-6" />
      <section>
        <h3>&copy; 2024 SyncTechX. Todos os direitos reservados.</h3>
      </section>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { ref, reactive } from "vue";
import { Button } from "./ui/button";
import { Card, CardHeader, CardContent, CardFooter } from "./ui/card";
import { Label } from "./ui/label";
import { Input } from "./ui/input";
import {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectTrigger,
  SelectValue,
} from "./ui/select";
import { Textarea } from "./ui/textarea";
import { Alert, AlertDescription, AlertTitle } from "@/components/ui/alert";

import { AlertCircle, Building2, Phone, Mail, Clock } from "lucide-vue-next";

interface ContactFormeProps {
  firstName: string;
  lastName: string;
  email: string;
  subject: string;
  message: string;
}

const contactForm = reactive<ContactFormeProps>({
  firstName: "",
  lastName: "",
  email: "",
  subject: "Desenvolvimento Web",
  message: "",
});

const invalidInputForm = ref<boolean>(false);

const handleSubmit = () => {
  const { firstName, lastName, email, subject, message } = contactForm;
  console.log(contactForm);

  const mailToLink = `mailto:nilton.novele@gmail.com?subject=${subject}&body=Olá, eu sou ${firstName} ${lastName}, o meu email é ${email}. %0D%0A${message}`;

  window.location.href = mailToLink;
};
</script>

<template>
  <section id="contact" class="container py-24 sm:py-32">
    <section class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <!-- Informações de contacto -->
      <div>
        <div class="mb-4">
          <h2 class="text-lg text-blue-500 mb-2 tracking-wider">Contacto</h2>
          <h2 class="text-3xl md:text-4xl font-bold">Fale Connosco</h2>
        </div>
        <p class="mb-8 text-muted-foreground lg:w-5/6">
          Precisa de um software? Fale connosco sem complicações. Ou tem uma
          ideia para uma plataforma que pode impulsionar o seu negócio?
        </p>

        <div class="flex flex-col gap-4">
          <div>
            <div class="flex gap-2 mb-1">
              <Building2 />
              <div class="font-bold">Onde estamos</div>
            </div>
            <div>Maputo, Moçambique | Cidade do Cabo, África do Sul</div>
          </div>

          <div>
            <div class="flex gap-2 mb-1">
              <Phone />
              <div class="font-bold">Telefone</div>
            </div>
            <div>+258 (84) 752-9665</div>
          </div>

          <div>
            <div class="flex gap-2 mb-1">
              <Mail />
              <div class="font-bold">Email</div>
            </div>
            <div>info@synctechx.com</div>
          </div>

          <div>
            <div class="flex gap-2">
              <Clock />
              <div class="font-bold">Horário</div>
            </div>
            <div>
              <div>Segunda a Sexta-feira</div>
              <div>08h00 - 16h00</div>
            </div>
          </div>
        </div>
      </div>

      <!-- Formulário -->
      <Card class="bg-muted/60 dark:bg-card">
        <CardHeader class="text-primary text-2xl"> </CardHeader>
        <CardContent>
          <form @submit.prevent="handleSubmit" class="grid gap-4">
            <div class="flex flex-col md:flex-row gap-8">
              <div class="flex flex-col w-full gap-1.5">
                <Label for="first-name">Nome próprio</Label>
                <Input
                  id="first-name"
                  type="text"
                  placeholder="Nilton"
                  v-model="contactForm.firstName"
                />
              </div>

              <div class="flex flex-col w-full gap-1.5">
                <Label for="last-name">Apelido</Label>
                <Input
                  id="last-name"
                  type="text"
                  placeholder="Novele"
                  v-model="contactForm.lastName"
                />
              </div>
            </div>

            <div class="flex flex-col gap-1.5">
              <Label for="email">Email</Label>
              <Input
                id="email"
                type="email"
                placeholder="nilton.novele@example.com"
                v-model="contactForm.email"
              />
            </div>

            <div class="flex flex-col gap-1.5">
              <Label for="subject">Assunto</Label>

              <Select v-model="contactForm.subject">
                <SelectTrigger>
                  <SelectValue placeholder="Selecione um assunto" />
                </SelectTrigger>
                <SelectContent>
                  <SelectGroup>
                    <SelectItem value="Desenvolvimento Web">
                      Desenvolvimento Web / Desktop
                    </SelectItem>
                    <SelectItem value="Desenvolvimento Mobile">
                      Desenvolvimento Mobile
                    </SelectItem>
                    <SelectItem value="Produtos Da SynctechX">
                      Produtos Da SynctechX
                    </SelectItem>
                    <SelectItem value="Consultoria TecnológicaT">
                      Consultoria Tecnológica
                    </SelectItem>
                    <SelectItem value="Segurança cibernética e hacking ético">
                      Segurança cibernética e hacking ético
                    </SelectItem>
                    <SelectItem value="IA e Automação">
                      IA e Automação
                    </SelectItem>
                    <SelectItem value="IA e Automação">
                      Reclamação / Sugestão
                    </SelectItem>
                  </SelectGroup>
                </SelectContent>
              </Select>
            </div>

            <div class="flex flex-col gap-1.5">
              <Label for="message">Mensagem</Label>
              <Textarea
                id="message"
                placeholder="A sua mensagem..."
                rows="5"
                v-model="contactForm.message"
              />
            </div>

            <Alert v-if="invalidInputForm" variant="destructive">
              <AlertCircle class="w-4 h-4" />
              <AlertTitle>Erro</AlertTitle>
              <AlertDescription>
                Há um erro no formulário. Verifique os seus dados.
              </AlertDescription>
            </Alert>

            <Button class="mt-4 bg-blue-600 text-white hover:bg-blue-700"
              >Enviar mensagem</Button
            >
          </form>
        </CardContent>
        <CardFooter></CardFooter>
      </Card>
    </section>
  </section>
</template>

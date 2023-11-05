<template>
  <base-form-section
    title="Perfil"
    description="Crie o seu perfil, informe alguma informação e acompanhe ao lado em tempo real."
  >
    <div class="shadow sm:overflow-hidden sm:rounded-md">
      <div class="space-y-6 bg-white px-4 py-5 sm:p-6">
        <div class="col-span-6 sm:col-span-3">
          <label for="name" class="block text-sm font-medium text-gray-700"
            >Nome</label
          >
          <input
            type="text"
            name="name"
            placeholder="Josué Juca"
            id="name"
            autocomplete="given-name"
            :value="name"
            @input="$emit('update:name', $event.target.value)"
            class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm"
          />
        </div>
        <div>
          <label for="about" class="block text-sm font-medium text-gray-700"
            >Sobre você</label
          >
          <div class="mt-1">
            <textarea
              id="about"
              name="about"
              rows="3"
              class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm placeholder-slate-400"
              placeholder="Meu nome é Juca e sou web development"
              maxlength="100"
              :value="desc"
              @input="$emit('update:desc', $event.target.value)"
            ></textarea>
          </div>
        </div>

        <div class="flex-grow col-span-6 sm:col-span-3">
          <label for="photo-url" class="block text-sm font-medium text-gray-700"
            >Foto de perfil</label
          >
          <input
            type="text"
            name="photo-url"
            id="photo-url"
            placeholder="https://imagem.com/exemplo.png"
            class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm"
            :value="image"
            @input="$emit('update:image', $event.target.value)"
          />
        </div>
      </div>
    </div>
  </base-form-section>
</template>
<script setup>
const props = defineProps(["name", "desc", "image"]);
</script>

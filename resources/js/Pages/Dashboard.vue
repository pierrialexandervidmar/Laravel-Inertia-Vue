<script setup>
import AppLayout from "@/Layouts/AppLayout.vue";
import Welcome from "@/Components/Welcome.vue";
</script>

<script>
import { Link } from '@inertiajs/vue3';
export default {
  props: {
    posts: Object,
  },
};
</script>

<template>
  <AppLayout title="Dashboard">
    <template #header>
      <h2 class="font-semibold text-xl text-gray-800 leading-tight">
        Lista de Postagens
      </h2>
    </template>

    <div class="py-12">
      <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
        <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
          <div class="mt-0 overflow-x-auto">
            <div
              class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg"
            >
              <table class="min-w-full divide-y divide-gray-300">
                <thead class="bg-gray-50">
                  <tr>
                    <th
                      scope="col"
                      class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900"
                    >
                      #ID
                    </th>
                    <th
                      scope="col"
                      class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900"
                    >
                      Título
                    </th>
                    <th
                      scope="col"
                      class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900"
                    >
                      Descrição
                    </th>
                    <th
                      scope="col"
                      class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900"
                    >
                      Ações
                    </th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="post in posts" :key="post.id">
                    <td class="px-3 py-4 whitespace-nowrap">{{ post.id }}</td>
                    <td class="px-3 py-4 whitespace-nowrap">
                      {{ post.title }}
                    </td>
                    <td
                      class="px-3 py-4 break-words max-w-xs sm:max-w-none whitespace-pre-wrap"
                    >
                      {{ post.content }}
                    </td>
                    <td class="px-3 py-4 whitespace-nowrap">
                      <a href="#" class="text-indigo-600 hover:text-indigo-900"
                        >Edit</a
                      >
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </AppLayout>
</template>

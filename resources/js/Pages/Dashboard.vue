<template>
  <AppLayout title="Dashboard">
    <template #header>
      <h2 class="font-semibold text-xl text-gray-800 leading-tight">
        Lista de Postagens <span v-if="$page.props.users.name"> - Olá {{ $page.props.users.name }}, seja bem vindo!</span>
      </h2>

    </template>


    <div class="py-12">

        <div v-if="$page.props.flash.message" class="text-blue-600 ml-12">
            {{ $page.props.flash.message }}
        </div>

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
                    <td>
                      <Link
                        :href="route('dashboard.edit', post.id)"
                        class="inline-flex items-center px-4 py-2 mr-4 border border-transparent text-sm font-medium rounded-md shadow-sm text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
                      >
                        Editar
                      </Link>
                    </td>

                    <td>
                      <button
                        @click="destroy(post.id)"
                        type="button"
                        class="inline-flex items-center px-4 py-2 mr-4 border border-transparent text-sm font-medium rounded-md shadow-sm text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
                      >
                        Apagar
                      </button>
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


<script setup>
import AppLayout from "@/Layouts/AppLayout.vue";
import Welcome from "@/Components/Welcome.vue";
</script>

<script>
import { Link } from "@inertiajs/vue3";
import { Inertia } from "@inertiajs/inertia"

export default {
  props: {
    posts: Object,
  },
  components: {
    Link
  },
  data() {
    const destroy = (id) => {
      if (confirm("Tem certeza que dezeja excluir o item " + id)) {
        Inertia.delete(route("dashboard.destroy", id));
      }
    }
    return {
      destroy
    };
  },
};
</script>
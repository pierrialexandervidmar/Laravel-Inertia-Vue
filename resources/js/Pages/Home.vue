<template>
    <Head>
        <title>Home</title>
    </Head>

    <div>
        <!-- This example requires Tailwind CSS v2.0+ -->
        <div class="px-4 sm:px-6 lg:px-8">
            <div class="sm:flex sm:items-center">
                <div class="sm:flex-auto mt-8">
                    <h1 class="text-xl font-semibold text-gray-900">
                        LISTAGEM DE POSTAGENS
                    </h1>
                </div>
                <hr />
                <menu-layout />
            </div>
            <div class="mt-8 overflow-x-auto">
                <div class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg">
                    <table class="min-w-full divide-y divide-gray-300">
                        <thead class="bg-gray-50">
                            <tr>
                                <th scope="col"
                                    class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">
                                    #ID
                                </th>
                                <th scope="col"
                                    class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">
                                    Título
                                </th>
                                <th scope="col"
                                    class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">
                                    Descrição
                                </th>
                                <th scope="col"
                                    class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">
                                    Ações
                                </th>
                            </tr>
                        </thead>
                        <tbody class="bg-white divide-y divide-gray-200">
                            <tr v-for="post in posts" :key="post.id">
                                <td class="px-3 py-4 whitespace-nowrap">{{ post.id }}</td>
                                <td class="px-3 py-4 whitespace-nowrap">{{ post.title }}</td>
                                <td class="px-3 py-4 break-words max-w-xs sm:max-w-none whitespace-pre-wrap">{{ post.content }}</td>
                                <td class="px-3 py-4 whitespace-nowrap">
                                    <a href="#" class="text-indigo-600 hover:text-indigo-900">Edit</a>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
import { Link } from '@inertiajs/vue3';
import MenuLayout from '../Layouts/LayoutMenu.vue'
export default {
    name: "PageHome",
    components: {
        Link,
        MenuLayout
    },
    props: {
        posts: Object,
    },
};
</script>

<style></style>

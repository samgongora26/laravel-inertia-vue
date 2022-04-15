<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
import Welcome from '@/Jetstream/Welcome.vue';
</script>

<template>
    <AppLayout title="Dashboard">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Módulo de notas
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="md:grid md:grid-cols-3 md:gap-6">
                    <div class="md:col-span-1">
                        <div class="px-4 sm:px0">
                            <h3 class="text-lg text-gray-900 ">Listado de notas</h3>
                            <p class="text-sm text-gray-600 ">Toma el registro correcto y ejecuta cualquier función (ver, editar o eliminar)</p>
                        </div>
                    </div>
                    <div class="md:col-span-2 mt-5 md:mt-0">
                        <div class="shadow bg-white mx:rounded-md p-4">
                            <Link :href="route('notes.create')" class="bg-blue-500 text-white font-bold py-2 px-4 my-3 mb-2 rounded-md">
                                Crear nota
                            </Link>
                            <table class="my-3">
                                <tr v-for="note in notes" :key="note.id_note">
                                    <td class="border px-4 py-2">
                                        {{ note.excerpt}}
                                    </td>
                                    <td class="px-4 py-2">
                                        <Link :href="route('notes.show', note.id)">
                                            Ver 
                                        </Link>
                                    </td>
                                    <td class="px-4 py-2">
                                        <Link :href="route('notes.edit', note.id)" class="">
                                            Editar
                                        </Link>
                                    </td>
                                    
                                </tr>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
    </AppLayout>
</template>

<script>
    export default{
        components:{
            AppLayout,

        },
        props:{
            notes: Array,
        },
    }
</script>
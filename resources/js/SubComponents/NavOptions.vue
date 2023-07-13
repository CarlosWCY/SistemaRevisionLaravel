<script setup>
import PanelMenu from "primevue/panelmenu";
import PanelMenuItem from "primevue/panelmenu";
import { Link } from "@inertiajs/vue3";

import {
    listItemsNavAplicationsAdministrator,
    listItemsNavAplicationsTeacher,
    listItemsNavAplicationsStudent,
    listItemsNavAplicationsGuest,
    listItemsNavDashboardAdministrator,
    listItemsNavDashboardTeacher,
    listItemsNavDashboardStudent,
    listItemsNavDashboardGuest,
} from "../constants/list-items-nav";

import { nextTick, ref } from 'vue';
const renderComponent = ref(true);

const forceRender = async () => {
  // Here, we'll remove MyComponent
  renderComponent.value = false;

   // Then, wait for the change to get flushed to the DOM
  await nextTick();

  // Add MyComponent back in
  renderComponent.value = true;
};

</script>

<template>

    <div v-if="is('Administrador')" class="flex flex-col gap-8">
        <div class="flex flex-col gap-4">
            <div class="ml-4 leading-4">
                <h2 class="text-[#818CF8] font-bold">Apliacaciones</h2>
                <span class="text-[#878B95] text-xs"
                    >Customizacion de componentes
                </span>
            </div>

            <ul class="space-y-1.5 font-medium">
                <li v-for="item in listItemsNavDashboardAdministrator">
                    <Link
                        v-bind:href="`${item.slug}`"
                        class="flex items-center py-3 px-4 text-gray-900 rounded-md dark:text-white hover:bg-white/10 dark:hover:bg-gray-700 gap-4 group"
                    >
                        <svg
                            aria-hidden="true"
                            class="w-6 h-6 text-gray-900 md:text-gray-400 transition duration-75 group-hover:text-white"
                            fill="currentColor"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 576 512"
                        >
                            <!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                            <path v-bind:d="`${item.svgPath}`" />
                        </svg>
                        <div class="group">
                            <span
                                class="text-gray-900 md:text-gray-300 text-sm font-bold hover:text-white group-hover:text-white capitalize"
                                >{{ item.name }}</span
                            >
                        </div>
                    </Link>
                </li>
            </ul>
        </div>
        <div class="flex flex-col gap-4">
            <div class="ml-4 leading-4">
                <h2 class="text-[#818CF8] font-bold">Otras Aplicaciones</h2>
                <span class="text-[#878B95] text-xs"
                    >Customizacion de componentes</span
                >
            </div>
            <ul class="space-y-1.5 font-medium">
                <li v-for="item in listItemsNavAplicationsAdministrator">
                    <Link
                        v-bind:href="`${item.slug}`"
                        class="flex items-center py-3 px-4 text-gray-900 rounded-md dark:text-white hover:bg-white/10 dark:hover:bg-gray-700 gap-4 group"
                    >
                        <svg
                            aria-hidden="true"
                            class="w-6 h-6 text-gray-900 md:text-gray-400 transition duration-75 group-hover:text-white"
                            fill="currentColor"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 576 512"
                        >
                            <!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                            <path v-bind:d="`${item.svgPath}`" />
                        </svg>
                        <div class="group">
                            <span
                                class="text-gray-900 md:text-gray-300 text-sm font-bold hover:text-white group-hover:text-white capitalize"
                                >{{ item.name }}</span
                            >
                        </div>
                    </Link>
                </li>
            </ul>
        </div>
    </div>

    <div v-if="is('Docente')" class="flex flex-col gap-8">
        <div class="flex flex-col gap-4">
            <div class="ml-4 leading-4">
                <h2 class="text-[#818CF8] font-bold">Apliacaciones</h2>
                <span class="text-[#878B95] text-xs"
                    >Customizacion de componentes
                </span>
            </div>

            <ul class="space-y-1.5 font-medium">
                <li v-for="item in listItemsNavDashboardTeacher">
                    <Link
                        v-bind:href="`${item.slug}`"
                        class="flex items-center py-3 px-4 text-gray-900 rounded-md dark:text-white hover:bg-white/10 dark:hover:bg-gray-700 gap-4 group"
                    >
                        <svg
                            aria-hidden="true"
                            class="w-6 h-6 text-gray-900 md:text-gray-400 transition duration-75 group-hover:text-white"
                            fill="currentColor"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 576 512"
                        >
                            <!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                            <path v-bind:d="`${item.svgPath}`" />
                        </svg>
                        <div class="group">
                            <span
                                class="text-gray-900 md:text-gray-300 text-sm font-bold hover:text-white group-hover:text-white capitalize"
                                >{{ item.name }}</span
                            >
                        </div>
                    </Link>
                </li>
            </ul>
        </div>
        <div class="flex flex-col gap-4">
            <div class="ml-4 leading-4">
                <h2 class="text-[#818CF8] font-bold">Otras Aplicaciones</h2>
                <span class="text-[#878B95] text-xs"
                    >Customizacion de componentes</span
                >
            </div>
            <ul class="space-y-1.5 font-medium">
                <li v-for="item in listItemsNavAplicationsTeacher">
                    <Link
                        v-bind:href="`${item.slug}`"
                        class="flex items-center py-3 px-4 text-gray-900 rounded-md dark:text-white hover:bg-white/10 dark:hover:bg-gray-700 gap-4 group"
                    >
                        <svg
                            aria-hidden="true"
                            class="w-6 h-6 text-gray-900 md:text-gray-400 transition duration-75 group-hover:text-white"
                            fill="currentColor"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 576 512"
                        >
                            <!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                            <path v-bind:d="`${item.svgPath}`" />
                        </svg>
                        <div class="group">
                            <span
                                class="text-gray-900 md:text-gray-300 text-sm font-bold hover:text-white group-hover:text-white capitalize"
                                >{{ item.name }}</span
                            >
                        </div>
                    </Link>
                </li>
            </ul>
        </div>
    </div>

    <div v-if="is('Estudiante')" class="flex flex-col gap-8">
        <div class="flex flex-col gap-4">
            <div class="ml-4 leading-4">
                <h2 class="text-[#818CF8] font-bold">Apliacaciones</h2>
                <span class="text-[#878B95] text-xs"
                    >Customizacion de componentes
                </span>
            </div>

            <ul class="space-y-1.5 font-medium">
                <li v-for="item in listItemsNavDashboardStudent">
                    <Link
                        v-bind:href="`${item.slug}`"
                        class="flex items-center py-3 px-4 text-gray-900 rounded-md dark:text-white hover:bg-white/10 dark:hover:bg-gray-700 gap-4 group"
                    >
                        <svg
                            aria-hidden="true"
                            class="w-6 h-6 text-gray-900 md:text-gray-400 transition duration-75 group-hover:text-white"
                            fill="currentColor"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 576 512"
                        >
                            <!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                            <path v-bind:d="`${item.svgPath}`" />
                        </svg>
                        <div class="group">
                            <span
                                class="text-gray-900 md:text-gray-300 text-sm font-bold hover:text-white group-hover:text-white capitalize"
                                >{{ item.name }}</span
                            >
                        </div>
                    </Link>
                </li>
            </ul>
        </div>
        <div class="flex flex-col gap-4">
            <div class="ml-4 leading-4">
                <h2 class="text-[#818CF8] font-bold">Otras Aplicaciones</h2>
                <span class="text-[#878B95] text-xs"
                    >Customizacion de componentes</span
                >
            </div>
            <ul class="space-y-1.5 font-medium">
                <li v-for="item in listItemsNavAplicationsStudent">
                    <Link
                        v-bind:href="`${item.slug}`"
                        class="flex items-center py-3 px-4 text-gray-900 rounded-md dark:text-white hover:bg-white/10 dark:hover:bg-gray-700 gap-4 group"
                    >
                        <svg
                            aria-hidden="true"
                            class="w-6 h-6 text-gray-900 md:text-gray-400 transition duration-75 group-hover:text-white"
                            fill="currentColor"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 576 512"
                        >
                            <!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                            <path v-bind:d="`${item.svgPath}`" />
                        </svg>
                        <div class="group">
                            <span
                                class="text-gray-900 md:text-gray-300 text-sm font-bold hover:text-white group-hover:text-white capitalize"
                                >{{ item.name }}</span
                            >
                        </div>
                    </Link>
                </li>
            </ul>
        </div>
    </div>

    <div v-if="is('Invitado')" class="flex flex-col gap-8">
        <div class="flex flex-col gap-4">
            <div class="ml-4 leading-4">
                <h2 class="text-[#818CF8] font-bold">Apliacaciones</h2>
                <span class="text-[#878B95] text-xs"
                    >Customizacion de componentes
                </span>
            </div>

            <ul class="space-y-1.5 font-medium">
                <li v-for="item in listItemsNavDashboardGuest">
                    <Link
                        v-bind:href="`${item.slug}`"
                        class="flex items-center py-3 px-4 text-gray-900 rounded-md dark:text-white hover:bg-white/10 dark:hover:bg-gray-700 gap-4 group"
                    >
                        <svg
                            aria-hidden="true"
                            class="w-6 h-6 text-gray-900 md:text-gray-400 transition duration-75 group-hover:text-white"
                            fill="currentColor"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 576 512"
                        >
                            <!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                            <path v-bind:d="`${item.svgPath}`" />
                        </svg>
                        <div class="group">
                            <span
                                class="text-gray-900 md:text-gray-300 text-sm font-bold hover:text-white group-hover:text-white capitalize"
                                >{{ item.name }}</span
                            >
                        </div>
                    </Link>
                </li>
            </ul>
        </div>
        <div class="flex flex-col gap-4">
            <div class="ml-4 leading-4">
                <h2 class="text-[#818CF8] font-bold">Otras Aplicaciones</h2>
                <span class="text-[#878B95] text-xs"
                    >Customizacion de componentes</span
                >
            </div>
            <ul class="space-y-1.5 font-medium">
                <li v-for="item in listItemsNavAplicationsGuest">
                    <Link
                        v-bind:href="`${item.slug}`"
                        class="flex items-center py-3 px-4 text-gray-900 rounded-md dark:text-white hover:bg-white/10 dark:hover:bg-gray-700 gap-4 group"
                    >
                        <svg
                            aria-hidden="true"
                            class="w-6 h-6 text-gray-900 md:text-gray-400 transition duration-75 group-hover:text-white"
                            fill="currentColor"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 576 512"
                        >
                            <!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                            <path v-bind:d="`${item.svgPath}`" />
                        </svg>
                        <div class="group">
                            <span
                                class="text-gray-900 md:text-gray-300 text-sm font-bold hover:text-white group-hover:text-white capitalize"
                                >{{ item.name }}</span
                            >
                        </div>
                    </Link>
                </li>
            </ul>
        </div>
    </div>

</template>

<script>
export default {
    props: {
        isMobile: Boolean,
    },
};
</script>

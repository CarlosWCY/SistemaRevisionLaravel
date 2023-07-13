<script setup>
import AppLayout from "@/Layouts/AppLayout.vue";
import Welcome from "@/Components/Welcome.vue";
import DataTable from "primevue/datatable";
import Column from "primevue/column";
import Button from "primevue/button";
import InputText from "primevue/inputtext";
import Dialog from "primevue/dialog";
</script>

<template>
    <AppLayout title="Dashboard">   
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Datatable
            </h2>
        </template>

        <div>
            <HeaderCard title="REVISAR TRABAJOS" />

            <div
                class="bg-white min-h-full overflow-hidden shadow-xl sm:rounded-lg p-4 flex flex-col border gap-8"
            >
                <h2 class="py-2 text-3xl text-center font-bold text-gray-800">
                    TRABAJOS ENTREGADOS
                </h2>

                
                <div class="card">
                    <DataTable
                        v-model:editingRows="editingRows"
                        editMode="row"
                        :value="customers"
                        paginator
                        :rows="6"
                        :rowsPerPageOptions="[5, 10, 20, 50]"
                        tableStyle="min-width: 50rem"
                        @row-edit-save="onRowEditSave"
                    >
                        <Column
                            field="name"
                            header="Nombre"
                            style="width: 25%"
                            sortable
                        >
                            <template #editor="{ data, field }">
                                <InputText v-model="data[field]" />
                            </template>
                        </Column>
                        <Column
                            field="country"
                            header="Pais"
                            style="width: 25%"
                            sortable
                        >
                            <template #editor="{ data, field }">
                                <InputText v-model="data[field]" />
                            </template>
                        </Column>
                        <Column
                            field="company"
                            header="Empresa"
                            style="width: 25%"
                            sortable
                        >
                            <template #editor="{ data, field }">
                                <InputText v-model="data[field]" /> </template
                        ></Column>
                        <Column
                            field="representative"
                            header="Representative"
                            style="width: 25%"
                            sortable
                        >
                            <template #editor="{ data, field }">
                                <InputText v-model="data[field]" /> </template
                        ></Column>
                       
                        
                        <Column  header="Revisar Tarea" :exportable="false" style="min-width:8rem">
                            <template #body="slotProps">
                                <Button icon="pi pi-pencil" outlined rounded class="mr-2" @click="visiblePdf = true" />
                            </template>
                        </Column>
                       
                        <Dialog
                        v-model:visible="visiblePdf"
                        modal
                        header=" "
                        :style="{ width: '80vw' }"
                        >
                        <Pdf initialDoc="https://pdftron.s3.amazonaws.com/downloads/pl/PDFTRON_about.pdf" ></Pdf>
                        </Dialog>  
                    </DataTable>
                </div>

                <!-- <Button label="Check" icon="pi pi-check" /> -->
            </div>
        </div>
    </AppLayout>
</template>

<script>
import { ref, onMounted } from "vue";
import HeaderCard from "../SubComponents/HeaderCard.vue";
import CustomForm from "../SubComponents/CustomForm.vue";
import Pdf from "./Pdf.vue";

const visible = ref(false);
const visiblePdf = ref(false);
const editingRows = ref([]);
const customers = ref([
    {
        name: "John ",
        country: "United States",
        company: "ABC Inc.",
        representative: "Jane Smith",
    },
    {
        name: "Alice Brown",
        country: "Canada",
        company: "XYZ Corp.",
        representative: "Bob Johnson",
    },
    {
        name: "Juan Quispe",

        country: "United States",

        company: "ABC Inc.",

        representative: "Jane Smith",
    },

    {
        name: "Pedro Mamani",

        country: "Canada",

        company: "XYZ Corp.",

        representative: "Bob Johnson",
    },

    {
        name: "Mary Smith",

        country: "Australia",

        company: "DEF Corp.",

        representative: "John Adams",
    },

    {
        name: "David Lee",

        country: "South Korea",

        company: "GHI Inc.",

        representative: "Sarah Kim",
    },

    {
        name: "Juan Perez",

        country: "Mexico",

        company: "JKL Corp.",

        representative: "Maria Garcia",
    },

    {
        name: "Mohammed Ali",

        country: "Egypt",

        company: "MNO Inc.",

        representative: "Fatima Ahmed",
    },

    {
        name: "Hans Schmidt",

        country: "Germany",

        company: "PQR Corp.",

        representative: "Anna Mueller",
    },

    {
        name: "Yuki Nakamura",

        country: "Japan",

        company: "STU Inc.",

        representative: "Taro Yamada",
    },

    {
        name: "Maria Rodriguez",

        country: "Spain",

        company: "VWX Corp.",

        representative: "Carlos Sanchez",
    },

    {
        name: "Lena Svensson",

        country: "Sweden",

        company: "YZA Inc.",

        representative: "Erik Johansson",
    },
]);

// onMounted(() => {
//     ProductService.getProductsMini().then((data) => (products.value = data));
// });

const ReviewPdf = (prod) => {
    visiblePdf = true;
};

const onRowEditSave = (event) => {
    let { newData, index } = event;

    customers.value[index] = newData;
};

const getStatusLabel = (status) => {
    switch (status) {
        case "INSTOCK":
            return "success";

        case "LOWSTOCK":
            return "warning";

        case "OUTOFSTOCK":
            return "danger";

        default:
            return null;
    }
};
const formatCurrency = (value) => {
    return new Intl.NumberFormat("en-US", {
        style: "currency",
        currency: "USD",
    }).format(value);
};

export default {
    components: {
        Button,
    },
    data() {
        return {
            count: 0,
        };
    },
    components: {
        DataTable,
        HeaderCard,
        InputText,
        Dialog,
        CustomForm,
    },
};
</script>

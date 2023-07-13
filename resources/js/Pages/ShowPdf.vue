<script setup>
import AppLayout from "@/Layouts/AppLayout.vue";
import Pdf from "./Pdf.vue";
import Welcome from "@/Components/Welcome.vue";
import DataTable from "primevue/datatable";
import Column from "primevue/column";
import Button from "primevue/button";
import Dialog from "primevue/dialog";
import HeaderCard from "../SubComponents/HeaderCard.vue";
</script>

<template>
    <AppLayout>
        hello jjj
        <Pdf initialDoc="https://pdftron.s3.amazonaws.com/downloads/pl/PDFTRON_about.pdf" ></Pdf>
    </AppLayout>
</template>


<script>
import Layout from "../../layouts/main";
import PageHeader from "@/components/page-header";


/**
 * Dashboard component
 */
export default {
  components: {
    Layout,
    PageHeader,

  },
  data() {
    return {
      title: "Dashboard",

    };
  }
};
</script>

<template>
  <Layout>
    <PageHeader :title="title" :items="items" />

  </Layout>
</template>
